# pawntilldawn 55

first thing first run PwnTillDawn.ovpn

<img width="946" height="665" alt="image" src="https://github.com/user-attachments/assets/9db3241f-4f6b-4b63-9764-6e984bf5afb5" />

this mean we already connected to the vpn, now we can start scanning run 

*nmap -sn 10.150.150.10-254

it will show all host are up!

<img width="643" height="853" alt="image" src="https://github.com/user-attachments/assets/7eb8724a-90dd-4734-8538-4eff67eeeef5" />

now we select one target host in this case i will using 10.150.150.55

*sudo nmap -A -p- -T4 10.150.150.55

<img width="628" height="421" alt="image" src="https://github.com/user-attachments/assets/f3abe9a1-ac2a-4c01-9c8d-d7d90a7db1a2" />

<img width="809" height="923" alt="image" src="https://github.com/user-attachments/assets/705752b2-05bd-4584-bd5f-c5457e56828f" />

we can see port 21 are open and it using vsftpd version now we can use metasploit to check for known vulnerablities

* sudo msfconsole -q
* search vsftpd
* exploit/unix/ftp/vsftpd_234_backdoor
* RHOST 10.150.150.55
* run

  <img width="629" height="164" alt="image" src="https://github.com/user-attachments/assets/2a3788e6-ebc8-43d9-a4bf-1b89a668cec6" />

so we can see no backdoor are exploitable because it already using vsftpd 3.0.3 version but it does say configured for " anonymous " only so that mean the username are anonymous and if we check in nmap the ftp are in code 230 which mean no password needed rather than code 530 where password are needed

<img width="555" height="194" alt="image" src="https://github.com/user-attachments/assets/6209de51-1395-43de-8bdc-2cfeb0812a5c" />


now we can login to ftp using " ftp 10.150.150.55 " when we are inside try run this command " ls -la " to see it's hidden files and also try cd /home , cd /etc and cd /var/www. now we can see there are "test files" now use command "get test" to download that files

<img width="620" height="458" alt="image" src="https://github.com/user-attachments/assets/3090c5a4-255d-4c4f-b073-aac8c947a2cd" />

once we cat the test file it said nothing here lol

<img width="229" height="58" alt="image" src="https://github.com/user-attachments/assets/8f74a6a3-c456-4750-b38c-16c53645e2d9" />



