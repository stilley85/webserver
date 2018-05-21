`import socket`

Imports the socket module.


`HOST, PORT = '', 8888`

Sets the hostname (identifier of a network interface) and port we will bind to our socket.


`listen_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)`

Creates our socket, which we pass 3 parameters:

* The socket family, here we use AF_INET which is IPv4. Other alternatives include AF_INET6 which is IPv6, AF_BLUETOOTH which is bluetooth and so more.

* The soket type, here we are using SOCK_STREAM which is TCP. SOCK_DGRAM would be UDP.

* The protocol. We don't pass one in this example so it defaults to 0.
