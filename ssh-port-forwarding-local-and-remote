
# Local port forwarding

This means you can access a remote port by local port.

`$ ssh -L 9000:localhost:80 user@example.com`

## An example: access a database server which can be only accessible by local

```
$ ssh -L 54322:localhost:5432 user@my-database-server-ip
$ psql -h localhost -p 54322
```

Now you can access local 54322 port to access the remote Postgres server (listening to localhost:5432)

# Remote port forwarding

This means public network can access your local port.

`$ ssh -L 8080:localhost:80 user@example.com`

Now the public user can access the server's 80 port, further forwarding to your local 8080 port for response.

There is one more thing you need to do to enable this. 
SSH doesn’t by default allow remote hosts to forwarded ports. 
To enable this open /etc/ssh/sshd_config and add the following line somewhere in that config file.

`GatewayPorts yes`

```
$ sudo vim /etc/ssh/sshd_config
$ sudo service ssh restart
```



