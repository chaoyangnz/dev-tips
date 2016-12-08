Using SSH’s ControlMaster feature you can give password only for the first session in a multiple ssh sessions. This lets you share multiple SSH sessions over a single network connection.

Add the following lines to the ~/.ssh/config file.

`$ vi ~/.ssh/config`

```
Host *
ControlMaster auto
ControlPath ~/.ssh/master-%r@%h:%p
Host * – all hosts
ControlPath ~/.ssh/master-%r@%h:%p – Path for creating the control file, make sure that this file is not accessible by others.
%r – remote login name
%h – host name ( remote )
%p – port
```

First time, when you perform SSH to a remote machine, you have to specify the password, which will create the master connection.

For further ssh, scp, or sftp sessions to the same machine, you don’t need to specify the password. This is true only when the master connection is alive. During that subsequent SSH connections, it will use the existing socket that was created from the first SSH connection.

To enable this feature for particular hosts, add the following to the ~/.ssh/config file.
```
Host 192.168.1.?
Host *.com
```
To change the control path:

`ControlPath ~/.mysecretfiles/master-%r@%h:%p`
You can also use ControlMaster attribute to control this behavior.

ControlMaster auto – This will automatically use the master connection for all succeeding connections.
ControlMaster autoask – This will ask for the confirmation for the next connection. If you say yes, it will use the same socket.
