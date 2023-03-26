# Server sent events

To run the server:

```
cargo run
```

To view the messages open `http://localhost:8080/` on your browser.

To see the event stream, go to the network tab an you should the `events`.

To send a broadcast message, send a post request:

```
http -f POST 127.0.0.1:8080/broadcast/hello
```

E.g broadcast logs

```
[2023-03-26T00:06:44Z INFO  sse] starting HTTP server at http://localhost:8080
[2023-03-26T00:06:44Z INFO  actix_server::builder] starting 2 workers
[2023-03-26T00:06:44Z INFO  actix_server::server] Actix runtime found; starting in Actix runtime
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000387
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000495
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000489
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000533
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000548
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000587
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000593
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000668
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000790
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000973
[2023-03-26T00:07:28Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.001086
[2023-03-26T00:07:29Z INFO  actix_web::middleware::logger] 127.0.0.1 "POST /broadcast/msg HTTP/1.1" 200 8 "-" "-" 0.000865
```

To close the event send a close message:

```
http -f POST 127.0.0.1:8080/broadcast/close
```
