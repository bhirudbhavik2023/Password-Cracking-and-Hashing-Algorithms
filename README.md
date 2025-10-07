# Password-Cracking-and-Hashing-Algorithms
Password Cracking and Hashing Algorithms and explanetion 
kali㉿kali)-[~]
└─$ cd /usr/share/wordlists
                                                                                       
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ ls 
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt.gz  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt      wifite.txt
                                                                                       
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ sudo gzip -d rockyou.txt.gz     
[sudo] password for kali: 
                                                                                       
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ ls
amass  dirbuster   fasttrack.txt  john.lst  metasploit  rockyou.txt  wfuzz
dirb   dnsmap.txt  fern-wifi      legion    nmap.lst    sqlmap.txt   wifite.txt
                                                                                       
┌──(kali㉿kali)-[/usr/share/wordlists]
└─$ cat rockyou.txt      
-----------------------------------------------------------------------------------------
**Password cracking with johntheripper
(kali㉿kali)-[~]
└─$ cd Desktop 
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ nano secret.txt
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ ls  
hash  secret.txt
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ zip -e secret.zip secret.txt
Enter password: 
Verify password: 
  adding: secret.txt (deflated 11%)
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
hash  secret.txt  secret.zip
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ unzip secret.zip
Archive:  secret.zip
[secret.zip] secret.txt password: 
replace secret.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: secret.txt              
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ zip2john secret.zip > zip.hash
ver 2.0 efh 5455 efh 7875 secret.zip/secret.txt PKZIP Encr: TS_chk, cmplen=43, decmplen=35, crc=D0E48171 ts=AB14 cs=ab14 type=8

(kali㉿kali)-[~/Desktop]
└─$ cat zip.hash
secret.zip/secret.txt:$pkzip$1*1*2*0*2b*23*d0e48171*0*44*8*2b*ab14*371e4f22b127e5d25cdff08715f82e565f63dfb6f1ff5d2f881023066ce665558d60675898ba95ed6dc5c0*$/pkzip$:secret.txt:secret.zip::secret.zip

(kali㉿kali)-[~/Desktop]
└─$ nano passwd.txt
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
hash  passwd.txt  secret.txt  secret.zip  zip.hash
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ sudo john -wordlist=passwd.txt zip.hash                                     
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
123456           (secret.zip/secret.txt)     
1g 0:00:00:00 DONE (2025-10-07 21:39) 100.0g/s 1300p/s 1300c/s 1300C/s david123
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

kali㉿kali)-[~/Desktop]
└─$ unzip secret.zip
Archive:  secret.zip
[secret.zip] secret.txt password: 
replace secret.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: r
new name: secret1
  inflating: secret1                 
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
hash  passwd.txt  secret1  secret.txt  secret.zip  zip.hash
                                                                                       
┌──(kali㉿kali)-[~/Desktop]
└─$ cat secret1 
This is a very very urgent massage
