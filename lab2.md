# Lab Report 2 - Servers and SSH Keys (Week 3)

---

## Part 1: ChatServer

The Chat Server was adapted from an existing program, NumberServer, which was included as part of the CSE 15L Wavelet repository from Week 2. The original NumberServer program can be viewed [here](https://github.com/ucsd-cse15l-f23/wavelet).

Here is the Server.java file responsible for actually handling connections to the server. This file is unchanged from the one used in NumberServer.
```java
// A simple web server using Java's built-in HttpServer

// Examples from https://dzone.com/articles/simple-http-server-in-java were useful references

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.net.URI;

import com.sun.net.httpserver.HttpExchange;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpServer;

interface URLHandler {
    String handleRequest(URI url);
}

class ServerHttpHandler implements HttpHandler {
    URLHandler handler;
    ServerHttpHandler(URLHandler handler) {
      this.handler = handler;
    }
    public void handle(final HttpExchange exchange) throws IOException {
        // form return body after being handled by program
        try {
            String ret = handler.handleRequest(exchange.getRequestURI());
            // form the return string and write it on the browser
            exchange.sendResponseHeaders(200, ret.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(ret.getBytes());
            os.close();
        } catch(Exception e) {
            String response = e.toString();
            exchange.sendResponseHeaders(500, response.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}

public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started!");
    }
}
```
Here is the ChatServer.java file responsible for actually processing the information to be modified and displayed based on incoming requests.
```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The string that gets modified by the incoming requests.
    String chatString = "";

    public String handleRequest(URI url) {
        // Requests are always of the form:
        // /add-message ? s=[MESSAGE] & user= [USER]
        String message = "";
        String user = "";
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");

            // The first parameter is the message (s=MESSAGE)
            String[] internalParam = parameters[0].split("=");
            message = internalParam[1];

            internalParam = parameters[1].split("=");
            user = internalParam[1];

            chatString += user + ": " + message + "\n";

            return chatString;
        } else {
            return "404 Not Found!";
        }
    }
}


// Reused from CSE15L Wavelet - NumberServer (Week 2 Lab)
class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

