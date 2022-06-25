# ***Read: Class 12 - Socket.io***

***

## **WebSocket:**

    It is a computer communications protocol, providing full-duplex communication channels over a single TCP connection. 

***

## **Describe the Web Socket request/response handshake and what happens once the connection is established.**

    The WebSocket protocol enables interaction between a web browser (or other client application) and a web server with lower overhead than half-duplex alternatives such as HTTP polling, facilitating real-time data transfer from and to the server. 

To establish a WebSocket connection, the client sends a WebSocket handshake request, for which the server returns a WebSocket handshake response as shown in picture below:

![]()

***

## **Socket.io Tutorial:**

    Socket.IO enables real-time bidirectional event-based communication. It works on every platform, browser or device, focusing equally on reliability and speed.

    Sockets work based on events. These are some reserved events, which can be accessed using the socket object on the server-side:

    Connect
    Message
    Disconnect
    Reconnect
    Ping
    Join
    Leave

    The client-side socket object also provides us with some reserved events:

    Connect
    Connect_error
    Connect_timeout
    Reconnect, etc.

## **Difference Between WebSocket and Socket.io:**

- WebSocket is the communication Protocol that provides bidirectional communication between the Client and the Server over a TCP connection; WebSocket remains open all the time, so they allow real-time data transfer. When clients trigger the request to the server, it does not close the connection on receiving the response; it rather persists and waits for the Client or server to terminate the request.

- Socket.IO is a library that enables real-time and full-duplex communication between the Client and the Web servers. It uses the WebSocket protocol to provide the interface. Generally, it is divided into two parts; both WebSocket vs Socket.io are event-driven libraries.

        Client-Side: it is the library that runs inside the browser
        Server Side: It is the library for Node.js

***

## **Key features of:**

WebSocket:

    WebSocket helps in real-time communication between the Client and the webserver.
    This protocol helps in transforming to cross-platform in a real-time world between the server and the client.
    This also enables the business worldwide for a real-time web application to enhance and increase the feasibility.
    The major advantage it stands over an HTTP connection that it provides full-duplex communication.

Socket.io:

    It helps in broadcasting to multiple sockets at a time and handles the connection transparently.
    It works on all platform, server or device, ensuring equality, reliability, and speed.
    It automatically upgrades the requirement to WebSocket if needed.
    It is a custom real-time transport protocol implementation on top of other protocols.
    It requires both libraries to be used Client side as well as a server-side library.
    IO works on work-based events. there are some reserved events that can be accessed using the Socket on the server side like Connect, message, Disconnect, Ping and Reconnect.
    There are some Client based reserved events like Connect, connect- error, connect-timeout and Reconnect etc.

[README](README.md)
