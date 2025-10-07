(Teletype Network) is a text-based network protocol used to connect to a computer remotely. Developed in 1969 and widely used in the early days of the Internet, it is specifically designed for interacting with network devices, servers or other endpoints.

The TELNET (Teletype Network) protocol is a network protocol for remote terminal connection. In simpler words, `telnet`, a TELNET client, allows you to connect to and communicate with a remote system and issue text commands. Although initially it was used for remote administration, we can use `telnet` to connect to any server listening on a TCP port number.

It provides a login interface with a username and password so that users can execute commands as if they were on the local terminal of that computer.

``` bash
telnet <SERVER-IP-ADDRESS> <PORT-NUMBER>
```

Default port 23