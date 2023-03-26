# Server sent events

To run the server:

```cargo run

```

To view the messages open `http://localhost:8080/` on your browser.

To see the event stream, go to the network tab an you should the `events`.

To send a broadcast message, send a post request:

```
http -f POST 127.0.0.1:8080/broadcast/hello
```

To close the event send a close message:

```
http -f POST 127.0.0.1:8080/broadcast/close
```
