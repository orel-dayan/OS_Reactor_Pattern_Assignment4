# **Operating System Course Assigment 4**

University assignment 4 for Operating System course in Ariel University.


#### __For more information, you can see in the PDF in the docs directory__.

## **Requirements**
- Ubuntu 22.04 LTS
- GNU C compiler
- Make


## **Description:**
The project is demonstration of a server that uses the Reactor design pattern to handle events generated by multiple clients. This means that it doesn't waste CPU cycles polling clients that have no new messages. Instead, it uses the OS's ability to "react" to events such as new client connections or incoming messages. The functionality of the reactor provided by shared library that linked to the server, the libary is not thread safe.

**How it works**:

- The server creates a socket and binds it to a port "9034" from beej guide.
- The server listens for incoming connections and accepts them.
- The server dynamically resizes its arrays to accommodate increasing numbers of clients
- The server handles multiple simultaneous client connections and broadcasts messages to all connected clients.
- The server properly cleans up resources when it receives an interrupt or terminate signal.

**NOTES:**
- We chose to write the project in c language.
- The beej program have errors in vscode but it works (it is very strange)
- For the client we used the telnet and nc commands : nc 127.0.0.1 9034 / telnet 127.0.0.1 9034
- libary is not thread safe.
- The server  can listen to 1024*8 clients at the same time . can be changed in the code in the macro MAX_CLIENTS.
- There are run examples in the docs directory .
- gnome_terminal_script.sh is create 100 clients and run them in the same time.


## **Run:**


```sh

  make all
  ./react_server
   ```

## *Links:*

* https://www.adamtornhill.com/Patterns%20in%20C%205,%20REACTOR.pdf - for the reactor design pattern.

* https://beej.us/guide/bgnet/examples/selectserver.c - from beej guide in Moodle.

* https://www.geeksforgeeks.org/socket-programming-in-cc-handling-multiple-clients-on-server-without-multi-threading/ - for the server.


