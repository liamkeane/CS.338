# Reverse Shell Assignment

Liam Keane

### Part 1: Installing a PHP web server

1. ```http
   http://danger.jeffondich.com/uploadedimages/lkeane-webshell.php?command=whoami
   ```
   
   www-data

2. It seems like the pre tags are meant to preserve whitespace and newline characters. When running the web shell without them the output is display as one continuous line.

### Part 2: Looking around

1. /var/www/danger.jeffondich.com/uploadedimages

2. root, daemon, bin, sys, sync, games, man, lp, mail, news, uucp, proxy, www-data, backup, list, irc, gnats, nobody, systemd-network, systemd-resolve, messagebus, systemd-timesync, syslog, _apt, tss, uuidd, tcpdump, usbmux, sshd, pollinate, landscape, fwupd-refresh, jeff, postgres, bullwinkle

3. No, I don't seem to have access since I get a connection reset message when I send the following url:

```http
danger.jeffondich.com/uploadedimages/lkeane-webshell.php?command=cat %2Fetc%2Fpasswd
```

4. It contains the hashed passwords for each of the users.

5. Secrets were found in these directories: /youwontfindthiswithgobuster/secret.txt, /secrets/kindasecret.txt, 

6. I found the underlying scripts running the page (I may have broken things).

### Part 3-4: Launching a reverse-shell

1. 10.0.2.15

```bash
hostname -I
```

1. 10.133.6.241. If we're using Kali then we want to be using Kali's IP address.

2. We can tell it's Kali because kali is the displayed user.

3. Kind of like escape characters, but for urls.

4. First of all, somehow uploading a webshell script to the target machine allows you to execute commands through http requests. The weird command that we run via this http method tells kali to initiate a connection with netcat (the ip and port) on my host machine by (I looked this part up) redirecting all commands to an instance of bash on kali's machine.










