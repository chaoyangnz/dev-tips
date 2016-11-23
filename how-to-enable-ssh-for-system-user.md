
# install sshd

`$ apt-get install ssh`

# edit /etc/ssh/sshd_config
```
PasswordAuthentication yes
PermitRootLogin yes
```

# restart service

`$ /etc/init.d/ssh restart`
