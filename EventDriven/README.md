# Event-Driven Programming in Node.js

## What is Event-Driven Programming ?

Event-Driven Programming is a logical pattern that we can choose to confine our programming within to avoid issues of complexity and collision.

## EventEmitter

- Example :-

```js
const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

function userJoined(username){
  // Assuming we already have a function to alert all users.
  alertAllUsers('User ' + username + ' has joined the chat.');
}

// Run the userJoined function when a 'userJoined' event is triggered.
chatRoomEvents.on('userJoined', userJoined);

function login(username){
  chatRoomEvents.emit('userJoined', username);
}
```

## Removing Listeners

- we remove it for this reasons:
  - Performance reasons.
  - Avoid memory leaks.

- To remove event listeners in EventEmitter we can use the removeListener or removeAllListeners method.

```js
const EventEmitter = require('events').EventEmitter;
const chatRoomEvents = new EventEmitter;

function displayMessage(message){
  document.write(message);
}

function userJoined(username){
  chatRoomEvents.on('message', displayMessage);
}

chatRoomEvents.on('userJoined', userJoined);

// Now if we want to remove the displayMessage function from the message event’s list of handlers:

chatRoomEvents.removeListener('message', 
displayMessage);
```

## Object Oriented Programming + Event-Driven Programming

```js
const Mailbox = {
  sendMail: function(){
    // code to send mail.
  },
  receiveMail: function(){
    // check server for new mail.
  }
}
```

-  imagine we have a hungry alligator, represented by the gator class. Using a non-event-driven approach, the process of eating for our alligator looks like this:

```js
class Food {
  constructor(name) {
    this.name = name;
  }

  becomeEaten() {
    return 'I have been eaten.';
  }
}

var bacon = new Food('bacon');

class gator {
  eat() {
    bacon.becomeEaten();
  }
}
```

- In this example, our gator had to access the methods inside of Food in order to eat. This is a lot of work for our lazy gator so we’re going to make things easier for him.

```js
const EventEmitter = require('events').EventEmitter;
const myGatorEvents = new EventEmitter;

class Food {
  constructor(name) {
    this.name = name;
    // Become eaten when gator emits 'gatorEat'
    myGatorEvents.on('gatorEat', this.becomeEaten);
  }

  becomeEaten(){
    return 'I have been eaten.';
  }
}

var bacon = new Food('bacon');

const gator = {
  eat() {
    myGatorEvents.emit('gatorEat');
  }
}
```

Now all our gator has to do is just say gatorEat and the EventEmitter takes care of the rest.
