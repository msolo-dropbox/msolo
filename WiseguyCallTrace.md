# Call Trace #

This illustration the order of operations when processing a request.

This is helpful when deciding how to alter the behavior of the base classes.

```
starting trace
 wsgiref.simple_server.WSGIServer ('serve_forever', 'SocketServer.py', 210)
   wsgiref.simple_server.WSGIServer ('_handle_request_noblock', 'SocketServer.py', 268)
     wsgiref.simple_server.WSGIServer ('get_request', 'SocketServer.py', 438)
     wsgiref.simple_server.WSGIServer ('verify_request', 'SocketServer.py', 293)
     wsgiref.simple_server.WSGIServer ('process_request', 'SocketServer.py', 301)
       wsgiref.simple_server.WSGIServer ('finish_request', 'SocketServer.py', 318)
         wsgiref.simple_server.WSGIRequestHandler ('__init__', 'SocketServer.py', 609)
           wsgiref.simple_server.WSGIRequestHandler ('setup', 'SocketServer.py', 652)
           wsgiref.simple_server.WSGIRequestHandler ('handle', 'wsgiref/simple_server.py', 127)
             wsgiref.simple_server.WSGIRequestHandler ('parse_request', 'BaseHTTPServer.py', 232)
             wsgiref.simple_server.WSGIRequestHandler ('get_stderr', 'wsgiref/simple_server.py', 124)
             wsgiref.simple_server.WSGIRequestHandler ('get_environ', 'wsgiref/simple_server.py', 87)
               wsgiref.simple_server.WSGIRequestHandler ('address_string', 'BaseHTTPServer.py', 478)
             wsgiref.simple_server.ServerHandler ('__init__', 'wsgiref/handlers.py', 384)
             wsgiref.simple_server.WSGIServer ('get_app', 'wsgiref/simple_server.py', 63)
             wsgiref.simple_server.ServerHandler ('run', 'wsgiref/handlers.py', 84)
               wsgiref.simple_server.ServerHandler ('setup_environ', 'wsgiref/handlers.py', 104)
                 wsgiref.simple_server.ServerHandler ('add_cgi_vars', 'wsgiref/handlers.py', 400)
                 wsgiref.simple_server.ServerHandler ('get_stdin', 'wsgiref/handlers.py', 394)
                 wsgiref.simple_server.ServerHandler ('get_stderr', 'wsgiref/handlers.py', 397)
                 wsgiref.simple_server.ServerHandler ('get_scheme', 'wsgiref/handlers.py', 140)
               ('hello_world_app', './test_app.py', 15)
                 wsgiref.simple_server.ServerHandler ('start_response', 'wsgiref/handlers.py', 166)
                   wsgiref.headers.Headers ('__init__', 'wsgiref/headers.py', 46)
               wsgiref.simple_server.ServerHandler ('finish_response', 'wsgiref/handlers.py', 125)
                 wsgiref.simple_server.ServerHandler ('result_is_file', 'wsgiref/handlers.py', 278)
                 wsgiref.simple_server.ServerHandler ('write', 'wsgiref/handlers.py', 207)
                   wsgiref.simple_server.ServerHandler ('send_headers', 'wsgiref/handlers.py', 269)
                 wsgiref.simple_server.ServerHandler ('finish_content', 'wsgiref/handlers.py', 248)
                 wsgiref.simple_server.ServerHandler ('close', 'wsgiref/simple_server.py', 30)
                   wsgiref.simple_server.WSGIRequestHandler ('log_request', 'BaseHTTPServer.py', 403)
                     wsgiref.simple_server.WSGIRequestHandler ('log_message', 'BaseHTTPServer.py', 427)
                       wsgiref.simple_server.WSGIRequestHandler ('address_string', 'BaseHTTPServer.py', 478)
                       wsgiref.simple_server.WSGIRequestHandler ('log_date_time_string', 'BaseHTTPServer.py', 464)
                   wsgiref.simple_server.ServerHandler ('close', 'wsgiref/handlers.py', 256)
           wsgiref.simple_server.WSGIRequestHandler ('finish', 'SocketServer.py', 657)
       wsgiref.simple_server.WSGIServer ('close_request', 'SocketServer.py', 446)
         <class 'socket._socketobject'> ('close', 'socket.py', 187)
```