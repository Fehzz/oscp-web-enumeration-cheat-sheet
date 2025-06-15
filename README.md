# OSCP Web Enumeration Cheat Sheet

This is a list of web enumeration tools and commands compiled to thoroughly enumerate web directories and services on a target machine. I am only sharing what I have personally used in CTFs and what's worked for me after hours of experimentation and testing.

**The objective is to discover all hidden directories and exploitable information while leaving no stone unturned.**

# Autorecon
---
Autorecon is the best way to start any web enumeration because with just one command, both TCP and UDP services are enumerated on the target. Autorecon uses various Nmap scripts and tools such as **dirbuster** & **Nikto** to do web enumeration.

Keep in mind that autorecon will *not* perform a UDP scan without **sudo / root privileges**. Furthermore, UDP scanning by default is limited to the top 100 known UDP ports. That should suffice for the OSCP, although you may want to further enumerate UDP beyond the top 100 ports.

To scan *both* TCP & UDP:
<pre>sudo autorecon $target </target> </pre>


  
