# adapt-socket

This is an Adapt **authoring tool plugin** which adds support for Web Sockets using Socket.io.

## Installation

1. Copy all sub-folders in `/routes/` to `/routes/` in your authoring tool folder.
2. Copy all sub-folders in `/frontend/` to `/frontend/src/plugins/` in your authoring tool folder.
3. Add the NPM dependencies in `dependencies.json` and run `npm install` to download them.

## Usage

### Common API

You will find the following functions on both the front-end and back-end socket plugins.

#### subscribe(callback[Function], actions[String/Array])

Adds a listener to the specified action(s). Callback function is called whenever a matching message is received.

In the case that actions is undefined, the listener function will receive _all_ socket messages.

**returns** the subscriber’s ID[Number].

#### unsubscribe(id[Number], actions[String/Array])

Removes the listener to the specified action(s). If no action is passed, the listener will be unsubscribed from all actions.

**returns** success[Boolean].

#### publish(action[String], data)

Sends a message via the socket server.


### Front-end

The front-end plugin registers itself to Notify, and thus can be accessed using `Origin.Notify.socket`.

#### isConnectionOpen()

**return** whether the client is connected to the socket server [Boolean]
