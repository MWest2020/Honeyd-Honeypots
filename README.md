# Honeypots
Repo for configs etc for sharing with fellow students

# Installation of OpenCanary





## `opencanary.conf`

You can find this file per default path in the `/etc/opencanaryd/` directory 

Depending on your honeypot needs, set the `conf` to make the honeypot more enticing:

Initially we set the conf to :

| Description                                                             | Configuration                                   |
|-------------------------------------------------------------------------|--------------------------------------------------|
| To make the honeypot more enticing                                     | ```json "http.enabled": true, ```               |
| To make the honeyport more enticing                                     | ```json "ssh.enabled": true,```                  |
| To provide a layer of authenticity of a corporate environment.           | ```"ftp.banner": "Logiopi FTP Server" ```        |
| To provide a layer of authenticity of a corporate environment.           | ```"http.banner": "Logiopi Web Server" ```       |
| To provide a layer of authenticity of a corporate environment.           | ```"ssh.version": "SSH-2.0-Logiopi_SSHD" ```     |
| Enable portscanning.                                                    | ```json "portscan.enabled": true ```             |


