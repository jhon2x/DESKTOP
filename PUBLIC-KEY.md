https://www.youtube.com/watch?v=5Fcf-8LPvws

john@uJohn:~$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/john/.ssh/id_rsa): 
/home/john/.ssh/id_rsa already exists.
Overwrite (y/n)? y
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/john/.ssh/id_rsa. -- your private key path
Your public key has been saved in /home/john/.ssh/id_rsa.pub. -- your public key path
The key fingerprint is:
SHA256:/gW/WTNolT5BUv0lu5Z681CHefOkdXn1kOG+cLNUlRc john@uJohn
The key's randomart image is:
+---[RSA 2048]----+
|              oE+|
|             o.+=|
|            . =o*|
|             +.*=|
|        S . . @=X|
|       .   o B+@*|
|        .   =o@ .|
|         . o.+o= |
|          . o. o.|
+----[SHA256]-----+


john@uJohn:~/.ssh$ sudo nano id_rsa.pub
