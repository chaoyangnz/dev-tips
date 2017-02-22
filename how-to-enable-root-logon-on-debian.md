`vi /etc/gdm3/daemon.conf`

Under security type `AllowRoot=true`

`vi /etc/pam.d/gdm-password`

Comment this line `auth required pam_succeed_if.so user != root quiet_success`

Now you should be able to login as root in you GUI Debian 8.
