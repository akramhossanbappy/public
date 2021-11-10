How to create password less authentication from windows to linux with ssh public key
============================================================================================
Step 1:
go to terminal from cmd and create your ssh key on windows machine

C:\Users\Bappy> ssh-keygen 

Step 2:
search .ssh/ folder on your windows pc 
it should be like 
~/.ssh/id_rsa.pub

Step 3: Create ssh key on linux server
root@ubuntuserver:~# ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /root/.ssh/id_rsa
Your public key has been saved in /root/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:D4aDdHGZlg53IXE5cKHkF7fwxVDyfMtHw94mRtpQZUI root@ubuntuserver
The key's randomart image is:
+---[RSA 3072]----+
|      . **B++=E.o|
|      .=*=+= Boo |
|    . .=o...+ +oo|
|   . o ...   =oo+|
|    . o S   . +++|
|       o o   . o.|
|          .      |
|                 |
|                 |
+----[SHA256]-----+

Step 4: Come back your windows machine then, copy your public key to linux machine 
C:\Users\Bappy> cat ~/.ssh/id_rsa.pub | ssh ubuntu@192.168.0.118 "cat >> ~/.ssh/authorized_keys"
