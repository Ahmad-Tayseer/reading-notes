# ***Read: Class 11 - Event-Driven Programming***

***

Event-Driven Programming makes use of the following concepts:

- An Event Handler is a callback function that will be called when an event is triggered.
- A Main Loop listens for event triggers and calls the associated event handler for that event.

***

## **EventEmitter:**

    It allows the user to get started incorporating Event-Driven Programming in the project right away.

***

## **How to work with EventEmitter?**

- Access the EventEmitter class through the events module.

        const EventEmitter = require('events').EventEmitter;
        const myEventEmitter = new EventEmitter;


- Write a function that will act as our event listener, then we can use EventEmitters on method to set the listener.

        const EventEmitter = require('events').EventEmitter;
        const chatRoomEvents = new EventEmitter;

        function userJoined(username){
        // Assuming we already have a function to alert all users.
        alertAllUsers('User ' + username + ' has joined the chat.');
        }

        // Run the userJoined function when a 'userJoined' event is triggered.
        chatRoomEvents.on('userJoined', userJoined);

- Make sure that our chat room triggers a userJoined event whenever someone logs in.

        function login(username){
        chatRoomEvents.emit('userJoined', username);
        }

## **Removing Listeners:**

- To remove event listeners in EventEmitter we can use the removeListener or removeAllListeners method.

- It’s important to note that in the EventEmitter that comes built-in with Node you must pass a reference to the exact function you wish to remove when using the removeListener method.

- It is often best to name your event handling functions and declaring them before you register the event listener, as opposed to leaving them anonymous.

For example:

        const EventEmitter = require('events').EventEmitter;
        const chatRoomEvents = new EventEmitter;

        function displayMessage(message){
        document.write(message);
        }

        function userJoined(username){
        chatRoomEvents.on('message', displayMessage);
        }

        chatRoomEvents.on('userJoined', userJoined);

***

## **Object Oriented Programming + Event-Driven Programming:**

- The Object Oriented approach promotes the idea that all behavior of an individual unit (or object) be handled from code within that unit.

- Using this approach, applications are built with many different units that all speak to and interact with each other.

Let’s imagine we have a hungry alligator, represented by the gator class. Using a non-event-driven approach, the process of eating for our alligator looks like this:

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

But in the below example, all our gator has to do is just say gatorEat and the EventEmitter takes care of the rest.

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

***

[README](README.md)
