# Message Queues

## Integrating Socket.IO

Socket.IO is composed of two parts:

A server that integrates with (or mounts on) the Node.JS HTTP Server socket.io
A client library that loads on the browser side socket.io-client

## Rooms

A room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:

![room](./img/rooms.png)

## Implementation details

The "room" feature is implemented by what we call an Adapter. This Adapter is a server-side component which is responsible for:

- storing the relationships between the Socket instances and the rooms
- broadcasting events to all (or a subset of) clients

You can find the code of the default in-memory adapter here.

Basically, it consists in two ES6 Maps:

- sids: Map<SocketId, Set<Room>>
- rooms: Map<Room, Set<SocketId>>

Calling socket.join("the-room") will result in:

- in the ̀sids Map, adding "the-room" to the Set identified by the socket ID
- in the rooms Map, adding the socket ID in the Set identified by the string "the-room"

Those two maps are then used when broadcasting:

- a broadcast to all sockets (io.emit()) loops through the sids Map, and send the packet to all sockets
- a broadcast to a given room (io.to("room21").emit()) loops through the Set in the rooms Map, and sends the packet to all matching sockets

You can access those objects with:

```js
// main namespace
const rooms = io.of("/").adapter.rooms;
const sids = io.of("/").adapter.sids;

// custom namespace
const rooms = io.of("/my-namespace").adapter.rooms;
const sids = io.of("/my-namespace").adapter.sids;
```

Notes:

- those objects are not meant to be directly modified, you should always use socket.join(...) and socket.leave(...) instead.
- in a multi-server setup, the rooms and sids objects are not shared between the Socket.IO servers (a room may only "exist" on one server and not on another).
