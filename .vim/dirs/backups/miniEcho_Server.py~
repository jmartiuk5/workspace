#!/usr/bin/env python

import socket

print "Starting up mini echo server"
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
sock.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
PORT = 4444
HOST = "127.0.0.1"

sock.bind((HOST, PORT))
sock.listen(5)

print "Awaiting connection from a client"
conn, addr = sock.accept()
print "Incoming connection From port:", addr

print "Starting ECHO output......"

data = "dummy"

while len(data):

    data = conn.recv(2048)
    print "Client sent: ", data
    conn.send(data)

print "closing connection"
conn.close()

print "Shutting down server"
sock.close()
