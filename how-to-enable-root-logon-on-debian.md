- Stay in root terminal and type “leafpad /etc/gdm3/daemon.conf”. This command opens the file “daemon.conf” in leafpad. Under security type “AllowRoot=true”. So your security section in the file should look like this:[security]
`AllowRoot=true` Once it looks like this save the file then exit the window.
Stay in root terminal and type “leafpad /etc/pam.d/gdm-password”. This command opens the file “gdm-password” in leafpad. Within this file you have comment out the line containing “auth required pam_succeed_if.so user != root quiet_success” so that it looks like this
#auth required pam_succeed_if.so user != root quiet_successSave the file and exit.
Now you should be able to login as root in you GUI Debian 8.
