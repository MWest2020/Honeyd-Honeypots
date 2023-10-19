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

## Getting notified

While OpenCanary had standard configuration for logging to be accessed for forensics on the honeypot network, you can set up a email as well. 

This is the section of the `opencanary.conf` you need to update the handler object for that:

```json
"SMTP": {
                    "class" : "logging.handlers.SMTPHandler",
                    "mailhost" : ["smtp.mail.com", 587],
                    "fromaddr" : "honeypot.notifier@mail.com",
                    "toaddrs" : ["honeypot.notifier@mail.com"],
                    "subject" : "OpenCanary Alert",
                    "credentials" : ["honeypot.notifier@mail.com", "your-email-password"],
                    
                }  
```

> **_Note_** : > for mail notifcation, you will need a `certfile`. Set one up with: `openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365
` and add to the object. You can skip everything after entering a passphrase while setting up the `certfile.pem`

