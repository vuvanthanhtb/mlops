# How-to Guide

In this tutorial, you will make a callback, which is simply an API so that the server can call after finishing the request.

## 1. Start the servers

First, start the callback by the following commands:

```shell
python webhook_server.py
```

, then open a new terminal and start your API server by

```shell
python main.py
```

## 2. Testing the application

Now, open the 3rd terminal, and send a request to your API server

```shell
python client.py
```
