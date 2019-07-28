---
published: true
title: Linux & mac admin tips & tricks
---

# Linux Mac tips

List of recipes to debug or just do what you need on MAC or LINUX machine.

## Find the pid of a listening process + kill it

I found this [Stackoverflow](http://stackoverflow.com/questions/24387451/how-can-i-kill-whatever-process-is-using-port-8080-so-that-i-can-vagrant-up) question.

On MAC

```text
lsof -i tcp:8018
```

display a table like that

```text
COMMAND  PID   USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
node    2091 slucas   21u  IPv4 0x55f00507a74a3aa5      0t0  TCP *:4506 (LISTEN)
```

To kill the process

```text
kill -9   2091
```

### ssh add ssh keys to authorized keys in a server

`cat ~/.ssh/id_rsa.pub | ssh root@your.ip.address "cat >> ~/.ssh/authorized_keys"`

authorized\_keys is file that list all authorized keys in the remote server.

for root login check that `PermitRootLogin without-password` is set in you sshdConfig file

[https://www.digitalocean.com/community/tutorials/how-to-use-ssh-keys-with-digitalocean-droplets](https://www.digitalocean.com/community/tutorials/how-to-use-ssh-keys-with-digitalocean-droplets)

