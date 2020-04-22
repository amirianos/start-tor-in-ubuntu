# start-tor-in-ubuntu
You should in first download and install tor with tirminal
Open the Linux terminal and enter the code below

```
sudo apt install tor
sudo apt install obfs4proxy
```
after this you should get Bridges
there is two way to get bridges:

1.https://bridges.torproject.org/

2.send get transport obfs4 to bridges@torproject.org
(tor reply to your email and it maybe go to your spam mails)

after that, change terminal's directory to torrc:

```
sudo nano /etc/tor/torrc
```
(in this part i use nano ,you can use any text editors instead of nano)

Go to the end of the file (/ + meta (alt)) and add these to the end of the file
```
UseBridges 1
ClientTransportPlugin obfs4 exec /usr/bin/obfs4proxy
Bridge obfs4 IP:PORT HASH-OF-YOUR-OBFS4-BRIDGE
```
(be sure to leave your own bridges and note that add "Bridge" before Bridge)
for save this changes press Ctrl+o and press Enter and finally for Exit press Ctrl+x

enter code below in terminal 
```
sudo systemctl restart tor@default.service
```

afer restart tor enter code below

```
journalctl -exft Tor
```
(this conmmand show you logs of tor)

if you can see line like this ```Bootstrapped 100%: Done```
you could connect to tor


for use tor in your browsers install extenssion Foxyproxy or in some browsers SwitchyOmega
and set SOCKS5 on 127.0.0.1:9050


It's ready .use it and enjoy freedom :P
