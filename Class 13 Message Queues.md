# ***Read: Class 13 - Message Queues***

***

## **Rooms:**

    It is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:

![]()

***

### **Joining and leaving.**

You can call join to subscribe the socket to a given channel:

    io.on("connection", (socket) => {
    socket.join("some room");
    });

And then simply use to or in (they are the same) when broadcasting or emitting:

    io.to("some room").emit("some event");

You can emit to several rooms at the same time:

    io.to("room1").to("room2").to("room3").emit("some event");

In that case, a union is performed: every socket that is at least in one of the rooms will get the event once (even if the socket is in two or more rooms).

You can also broadcast to a room from a given socket:

    io.on("connection", (socket) => {
    socket.to("some room").emit("some event");
    });

In that case, every socket in the room excluding the sender will get the event.

Broadcasting to all clients in a room excepting the sender.
To leave a channel you call leave in the same fashion as join.

![]()

***

### **Disconnection:**

Upon disconnection, sockets leave all the channels they were part of automatically, and no special teardown is needed on your part.

You can fetch the rooms the Socket was in by listening to the disconnecting event:

    io.on("connection", socket => {
    socket.on("disconnecting", () => {
        console.log(socket.rooms); // the Set contains at least the socket ID
    });

        socket.on("disconnect", () => {
            // socket.rooms.size === 0
        });
    });

***
***

## **Namespaces:**

A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing").

![]()

Each namespace has its own:

event handlers:

    io.of("/orders").on("connection", (socket) => {
    socket.on("order:list", () => {});
    socket.on("order:create", () => {});
    });

    io.of("/users").on("connection", (socket) => {
    socket.on("user:list", () => {});
    });

rooms:

    const orderNamespace = io.of("/orders");

    orderNamespace.on("connection", (socket) => {
    socket.join("room1");
    orderNamespace.to("room1").emit("hello");
    });

    const userNamespace = io.of("/users");

    userNamespace.on("connection", (socket) => {
    socket.join("room1"); // distinct from the room in the "orders" namespace
    userNamespace.to("room1").emit("holà");
    });

middlewares:

    const orderNamespace = io.of("/orders");

    orderNamespace.use((socket, next) => {
    // ensure the socket has access to the "orders" namespace, and then
    next();
    });

    const userNamespace = io.of("/users");

    userNamespace.use((socket, next) => {
    // ensure the socket has access to the "users" namespace, and then
    next();
    });

***

[README](README.md)
