# Securing Passwords

Cryptographic hash algorithms MD5, SHA1, SHA256, SHA512, SHA-3 are general purpose hash functions, designed to calculate a digest of huge amounts of data in as short a time as possible. Hashing is the greatest way for protecting passwords and considered to be pretty safe for ensuring the integrity of data or password.

## What The Benefit Of Using Hashing ?

The benefit of hashing is that if someone steals the database with hashed passwords, they only make off with the hashes and not the actual plaintext passwords.

## There are some weaknesses in cryptographic hash algorithm mention some of them :-

- **Brute Force attack** : Hashes can't be reversed, so instead of reversing the hash of the password, an attacker can simply keep trying different inputs until he does not find the right now that generates the same hash value.

- **Hash Collision attack** : Hash functions have infinite input length and a predefined output length, so there is inevitably going to be the possibility of two different inputs that produce the same output hash. MD5, SHA1, SHA2 are vulnerable to Hash Collision Attack i.e. two input strings of a hash function that produce the same hash result.

## What is the BCrypt?

***BCrypt, IT's SLOW AND STRONG AS HELL***

- **Bcrypt** : is an adaptive hash function based on the Blowfish symmetric block cipher cryptographic algorithm and introduces a work factor (also known as security factor), which allows you to determine how expensive the hash function will be.

---

## Basic access authentication

- basic access authentication is a method for an HTTP user agent (e.g. a web browser) to provide a user name and password when making a request.

- HTTP Basic authentication (BA) implementation is the simplest technique for enforcing access controls to web resources because it does not require cookies, session identifiers, or login pages; rather, HTTP Basic authentication uses standard fields in the HTTP header.

- The BA mechanism does not provide confidentiality protection for the transmitted credentials. They are merely encoded with Base64 in transit and not encrypted or hashed in any way.

## mention a method that clear cached credentials in certain web browsers :-

- redirecting the user to a URL on the same domain, using credentials that are intentionally incorrect. However, this behavior is inconsistent between various browsers and browser versions.

## Protocol :-

- **Server side**: When the server wants the user agent to authenticate itself towards the server after receiving an unauthenticated request, it must send a response with a HTTP 401 Unauthorized status line and a WWW-Authenticate header field.

       WWW-Authenticate: Basic realm="User Visible Realm" 

       WWW-Authenticate: Basic realm="User Visible Realm", charset="UTF-8"

- **Client side** :When the user agent wants to send authentication credentials to the server, it may use the Authorization header field.

- The Authorization header field is constructed as follows:

1. The username and password are combined with a single colon (:). This means that the username itself cannot contain a colon.

2. The resulting string is encoded into an octet sequence. The character set to use for this encoding is by default unspecified, as long as it is compatible with US-ASCII, but the server may suggest use of UTF-8 by sending the charset parameter.

3. The resulting string is encoded using a variant of Base64 (+/ and with padding).

4. The authorization method and a space (e.g. "Basic ") is then prepended to the encoded string.

        For example, if the browser uses Aladdin as the username and open sesame as the password, then the field's value is the Base64 encoding of Aladdin:open sesame, or QWxhZGRpbjpvcGVuIHNlc2FtZQ==. Then the Authorization header field will appear as:

        Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==

---

## OWASP auth cheatsheet :-

- **Authentication** : is the process of verifying that an individual, entity or website is whom it claims to be. Authentication in the context of web applications is commonly performed by submitting a username or ID and one or more items of private information that only a given user should know.

- **Session Management** : is a process by which a server maintains the state of an entity interacting with it. This is required for a server to remember how to react to subsequent requests throughout a transaction. Sessions are maintained on the server by a session identifier which can be passed back and forward between the client and server when transmitting and receiving requests. Sessions should be unique per user and computationally very difficult to predict. The Session Management Cheat Sheet contains further guidance on the best practices in this area.

---

## npm

- npm i bcrypt

## Usage

```js

async (recommended)
const bcrypt = require('bcrypt');
const saltRounds = 10;
const myPlaintextPassword = 's0/\/\P4$$w0rD';
const someOtherPlaintextPassword = 'not_bacon';
```

- To hash a password:

```js 
Technique 1 (generate a salt and hash on separate function calls):

bcrypt.genSalt(saltRounds, function(err, salt) {
    bcrypt.hash(myPlaintextPassword, salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
```

```js 

Technique 2 (auto-gen a salt and hash):

bcrypt.hash(myPlaintextPassword, saltRounds, function(err, hash) {
    // Store hash in your password DB.
});
```

```js 
To check a password:
// Load hash from your password DB.
bcrypt.compare(myPlaintextPassword, hash, function(err, result) {
    // result == true
});
bcrypt.compare(someOtherPlaintextPassword, hash, function(err, result) {
    // result == false
});
```

**[bcrypt docs](https://www.npmjs.com/package/bcrypt)**
