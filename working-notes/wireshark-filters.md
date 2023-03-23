# WireShark filters

Lists packets with IP address of specified value

Lists packets with destination IP address of specified value

Lists packets with source address IP of specified value

Lists packets with TCP ports of specified value

Lists packets with UDP ports of specified value

Filters all HTTP GET and POST requests

Shows the responses to the HTTP requests, including the response codes

Sets a filter to display all packets that contain DNS data

Displays all TCP packets that contain a string matching whatever is defined as

Show any packet with Specific IP (example 10.0.01)

how any TCP packet with Specific Port (example port 22)

Show packets to and from any address in a subnet

Show all protocol traffic (example HTTP port 80)

`tcp.port == 80 and ip.addr == 10.0.0.1`

Show specific traffic to/from specific IP address (HTTP on example 10.0.0.1 )

`http.request.method == “POST”`

Filter for HTTP POST Requests

`http.request.method == “GET”`

Filter for HTTP GET Requests

`http.response.code == 200`

Show specific response request (example 200)

Show all packets that contain the word ‘traffic’
