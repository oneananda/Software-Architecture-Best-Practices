# Keep-Alive

Keep-Alive is used to maintain already established connections by sending the requests to the server saying that the connection is alive.

### HTTP Keep-Alive
HTTP Keep-Alive allows a single TCP connection to be used for multiple HTTP requests/responses instead of opening a new connection for each request.

By reusing the same connection, the overhead of establishing new TCP connections (which involves a handshake process) is eliminated.

In HTTP/1.1, Keep-Alive is enabled by default, meaning the server will keep the connection open after sending a response. Clients can send additional requests over the same connection until either the client or the server closes the connection.

### TCP Keep-Alive
To maintain a continued connection by sending small "keep-alive" packets at regular intervals.

