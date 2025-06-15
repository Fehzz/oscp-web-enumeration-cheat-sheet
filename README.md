# (Work In Progess) OSCP Web Enumeration Cheat Sheet

This is a list of web enumeration tools and commands compiled to thoroughly enumerate web directories and services on a target machine. I am sharing what I have personally used in CTFs and whatever knowledge I have gained after hours of experimentation and testing.

**The objective is to discover all hidden directories and exploitable information while leaving no stone unturned.**

# Autorecon
Autorecon is a clinical web enumeration tool that is very easy to deploy. With just one command, TCP services are enumerated thoroughly on the target. Autorecon uses various Nmap scripts and tools such as **dirbuster** & **Nikto** for web enumeration (if a web service is running at all on the target). 

Autorecon, at least in my experience, can take up to 10 minutes or a little longer. You might want to get a quicker Nmap scan out of the way to kickstart your enumeration as Autorecon does it's thing in the background.

Keep in mind that autorecon is also capable of enumerating UDP but it will *not* perform a UDP scan without **sudo / root privileges**. UDP is not relevant as far as the purpose of this cheat sheet is concerned as we are focused solely on web enumeration.

To scan TCP ports:
<pre>autorecon $target </target> </pre>

Once an HTTP port is discovered, autorecon will run various tools and scans against the target at that specific port:
![image](https://github.com/user-attachments/assets/31bce66e-9d81-4396-b0a2-73fab431f37c)

Autorecon will automatically save the results by default into a directory named "results" which will have sub-directories dedicated to each port. In this case, a sub-directory tcp80 is created which will include results from feroxbuster, cURL, Nikto, Nmap and Whatweb.

![image](https://github.com/user-attachments/assets/25a6aa4f-7acd-4031-987a-980586d84835)

Autorecon is able to identify potential exploits too, as seen in the _patterns.log file found in the **scans** sub-directory. Reference screenshot below:

![image](https://github.com/user-attachments/assets/69e556bc-6c25-4771-a602-ad01ae207464)

  
