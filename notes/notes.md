# Section 1 : Introduction
course sections :
- hacking lab
- python intro
- reconnaissance (nmap) & scanning
- vulnerbaility analysis
- exploit (use of metasploit on kali)
- post-exploit
- website pen-test (brute force scripts)
- man-in-the-middle
- wifi cracking

differences white hat VS black hat

# Section 2 : setup hacking lab
## setup hyperV kali vm
- get full-screen :
```
In /etc/default/grub change GRUB_CMDLINE_LINUX_DEFAULT=”quiet” to GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash video=hyperv_fb:your_resolution″ for me it was GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash video=hyperv_fb:1920×1080″. Save file then run sudo update-grub and restart.
```
 [source](https://unix.stackexchange.com/questions/491737/how-to-enable-the-full-screen-mode-for-kali-linux-on-hyper-v-virtual-machine)

create an external switch and 
```
sudo dhclient -v -r and sudo dhclient -v
```
[source](https://superuser.com/questions/469806/windows-8-hyper-v-how-to-give-vm-internet-access)

##  stages of pen-test
1. Reconnaissance/data gathering
objectives : plan attack
web search + 

2. Scanning
objectives : list assets + vulnerbilities
nmap

3. exploitation/Gaining acces
exploit cve

4. maintaining access
optionnal : install rootkit/backdoor

5. covreing tracks
rm logs/files, revert changes, etc.

# Section 3 : *-nix OS intro

# Section 4 : Reconnaissance/data gathering
Active infos gathering != Passive infos gathering

## Active infos gathering
- use of kali tools
- get data from target (GET requests, talk with target employee=social engeineering, etc.)

## Passive infos gathering
- use of kali tools
- use of a middle source (google, website, etc.) = no direct contact with contact

## objectives
- ip ranges
- technologies/tools used by target
- phones

## get ip address
ipv6 adress :
```
ping google.com
```
ipv4 address :
```
ping google.com -4
```
nslookup = query DNS
whois <website adress or ip> = get whois data

## whatweb tool : stealthy website scan
- get technos run by website (lamp stack, etc.)
- warning : do not perform aggressive scan without authouriwation
cmd = `whatweb reddit.com -v`

## ip range scan
cmd = `whatweb 192.168.1.0/24 --aggression 3 -v --no-errors --log-verbose=file.txt`

## gathering email with theHarvester and hunters.io
cmd = `theHarvester -d <domain> -b all -l 200`
or use hunter.io


## Get additional tools
[top 25 OSINT tools for pro](https://securitytrails.com/blog/osint-tools)
- [red hawk](https://github.com/Tuhinshubhra/RED_HAWK) : "All in one tool for Information Gathering and Vulnerability Scanning"
list of DNS records [source](https://simpledns.plus/help/dns-record-types) :
    A (Host address)
    AAAA (IPv6 host address)
    ALIAS (Auto resolved alias)
    CNAME (Canonical name for an alias)
    MX (Mail eXchange)
    NS (Name Server)
    PTR (Pointer)
    SOA (Start Of Authority)
    SRV (location of service)
    TXT (Descriptive text)
cmd = `php rhawk.php`

- [sherlock](https://github.com/sherlock-project/sherlock) : " Hunt down social media accounts by username across social networks"
cmd = `python sherlock <username>`

# Section 5 : scanning
- focus on tech side of data gathering
- **WARNING** : it's forbiden to scan, so use honeypot or local virtualized vulnerable assets for training purpose
- objectives
1. look for open ports (80:web + 443 for ssl ; 21:ftp ; 22:ssh ; 53:DNS ; 25:smtp)

## TCP & UDP protocols
- TCP = most common on internet (tansfer protocol protocol)
1. (a->b) SYN : ask to establish conn
2. (b->a) SYN/ACK
3. (a->b) ACK : establish conn
TCP garantee packet are received and received in order + resend if fail/corruption/errors

- UDP (user datagram protocol)
no reception garanty, tradeof = much faster than TCP
use for broadcast/live/etc.

## setup vulnerable machines
- https://www.rapid7.com/blog/post/2011/12/23/where-can-i-find-vulnerable-machines-for-my-penetration-testing-lab/
install ssh on kali
```
sudo apt-get install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
```
