# Connecting To Gateway

You can connect to the gateway at any time, but to actually do stuff, you must have a `User Token` which you can get by [Logging In](/Logging-In.md).

To connect, make a Websocket at the url:

`wss://gateway.discord.gg/`

> <h4><b>IMPORTANT:</b></h4> If you are resuming a connection, make sure to use the <code>resume_gateway_url</code> you recieved in your READY event

With the query parameters:

```Connection Options
V (The API Version):
    - 1-5 (Discontinued (WILL ERROR 400))
    - 6-8 (Deprecated)
    - 9 (Available)
    - 10 (Recommended)
Encoding (The Encoding To Use): "json" | "etf"
Compress (OPTIONAL: Whether To Compress The Data Sent/Recieved): "zlib-stream"
```

Upon successful connection, you should immediately recieve an [Opcode 10 Hello](/Gateway/Opcodes.md?id=_10-hello).

Once you recieve an [Opcode 10 Hello](/Gateway/Opcodes.md?id=_10-hello), you should proceed to send an [Opcode 2 Identify](/Gateway/Opcodes.md?id=_2-identify) using your `User Token` as the `token`.

> If you fail to Identify (Normally because you have an invalid token), you will recieve an [Opcode 9 Invalid Session](/Gateway/Opcodes.md?id=_9-invalid-session), and you must [Log In](/Logging-In.md) again.

After successful identification, you should recieve a READY event through an [Opcode 0 Dispatch Event](/Gateway/Opcodes.md?id=_0-dispatch-event)

After getting a READY event, you should wait about 5-10 seconds before sending an [Opcode 1 Heartbeat](/Gateway/Opcodes.md?id=_1-heartbeat).

Then, repeatedly send another [Opcode 1 Heartbeat](/Gateway/Opcodes.md?id=_1-heartbeat) on an interval of every (Your `heartbeat_interval` from the [Opcode 10 Hello](/Gateway/Opcodes.md?id=_10-hello)) milliseconds.
