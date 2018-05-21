`import socket`

Imports the socket module.


`HOST, PORT = '', 8888`

Sets the hostname (identifier of a network interface) and port we will bind to our socket.


`listen_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)`

Creates our socket, which we pass 3 parameters:

* The socket family, here we use AF_INET which is IPv4. Other alternatives include AF_INET6 which is IPv6, AF_BLUETOOTH which is bluetooth and so on.

* The soket type, here we are using SOCK_STREAM which is TCP. SOCK_DGRAM would be UDP.

* The protocol. We don't pass one in this example so it defaults to 0.

We now have a socket object.

`listen_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)`

we can use .socket.setsockopt() to set the value of a given socket option.

There are 3 required functions to create our server program. These Server Socket Methods are s.bind(), s.listen() and s.accept().

`listen_socket.bind((HOST, PORT))`

We bind the hostname and port values we set earlier to the socket.

`listen_socket.listen(1)`

We set up and start TCP listener.

`print 'Serving HTTP on port %s ...' % PORT`

`while True:`
`client_connection, client_address = listen_socket.accept()`
`request = client_connection.recv(1024)`
`print request`

http_response = """\
HTTP/1.1 200 OK

Hello, World!
"""

`client_connection.sendall(http_response)`
`client_connection.close()`
