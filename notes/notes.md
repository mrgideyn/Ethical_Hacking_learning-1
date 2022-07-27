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