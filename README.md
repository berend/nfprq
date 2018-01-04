# nfprq
nfprq stands for no-frills python redis queue

Scope is creating a very simple queueing framework, that just needs redis and nothing more.


This README just describes how nfprq will be used later and a list of features and non-features


## Usage

A simple producer should look like this:

```python
queue = Nfprq("queuename", redis_instance)

message = '{"foo": "bar"}'  # this is a string

queue.enqueue(message)

```


A consumer should look like this

```python
queue = Nfprq("queuename", redis_instance)

while True:
    message = queue.consume()
    # do stuff

```

That's it!


## Features
* enqueue
* consume

## Maybe feature

* message ack & requeue


## Non features

Stuff that is not going to be implemented

* automatic dead lettering
* routing, topics and the like
* fancy decorators
* command line runners and the like (use supervisor or similar to run consumers)

