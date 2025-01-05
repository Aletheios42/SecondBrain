**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Lesson1
# Guided Exercises
##### 1. Logged in as user sonya on your client machine, carry out the following SSH tasks on the remote server halof:
◦ Execute the command to list the contents of ~/.ssh as user serena on the remote host; then return to your local terminal.
R: ssh serena@halof ls .ssh
◦ Login as user serena on the remote host.
R: ssh serena@halof
◦ Login as user sonya on the remote host.
R: ssh halof
◦ Delete all keys belonging to halof from your local ~/.ssh/known_hosts file.
R:  ssh-keygen -R halof
◦ On your client machine, create an ecdsa key pair of 256 bits.
R: ssh-keygen -t ecdsa -b 256
◦ On your client machine, create an ed25519 key pair of 256 bits.
R: ssh-keygen -t ed25519
##### 2. Put the following steps in the right order to establish an SSH connection using the SSH authentication agent:
◦ On the client, start a new Bash shell for the authentication agent with ssh-agent /bin/bash.
◦ On the client, create a key pair using ssh-keygen.
◦ On the client, add your private key to a secure area of memory with ssh-add.
◦ Add your client’s public key to the ~/.ssh/authorized_keys file of the user you want to login as on the remote host.
◦ If it does not already exist, create ~/.ssh for the user you want to login as on the server.
◦ Connect to the remote server.
The correct order is:
Step 1: On the client, create a key pair using ssh-keygen.
Step 2: If it does not already exist, create ~/.ssh for the user you want to login as on the server.
Step 3: Add your client’s public key to the ~/.ssh/authorized_keys file of the user you want to login as on the remote host.
Step 4: On the client, start a new Bash shell for the authentication agent with ssh-agent /bin/bash.
Step 5: On the client, add your private key to a secure area of memory with ssh-add.
Step 6: Connect to the remote server.
##### 3. Regarding port forwarding, what option and directive is used for the following tunnel types:
- R:

| Tunnel Type       | Option | Directive                       |
| ----------------- | ------ | ------------------------------- |
| Local             | -L     | localport:remotehost:remoteport |
| Remote or Reverse | -R     | remoteport:localhost:localport  |
| X                 | -X     | N/A (enables X11 forwarding)    |
##### 4. Suppose you type the command ssh -L 8888:localhost:80 -Nf ina@halof into the terminal of your client machine. Still on the client machine, you point a browser to http://localhost:8888. What will you get?
- R:  The webserver’s homepage of halof, as localhost is understood from the server’s perspective.
# Explorational Exercises
##### 1. Concerning SSH security directives:
◦ What directive is used in /etc/ssh/sshd_config to enable root logins:
R: PermitRootLogin
◦ What directive would you use in /etc/ssh/sshd_config to specify only a local account to accept SSH connections:
 R: AllowUsers
##### 2. When using the same user on both the client and the server, what ssh command can you use to transfer the client’s public key over to the server so that you can login through public key authentication?
- R: ssh-copy-id
##### 3. Create two local port tunnels in a single command forwarding local unprivileged ports 8080 and 8585 through remote server halof to the websites www.gnu.org and www.melpa.org, respectively. Use user ina on the remote server and do not forget to use the -Nf switches:
- R: ssh -L 8080:www.gnu.org:80 -L 8585:www.melpa.org:80 -Nf ina@halof

# Lesson2
# Guided Exercises
##### 1. Complete the table by providing the correct filename:
| Description                           | Filename          |
| ------------------------------------- | ----------------- |
| Trust database                        | trustdb.gpg       |
| Directory for revocation certificates | opengp-revocs.d   |
| Directory for private keys            | private-keys-v1.d |
| Public keyring                        | pubring.kbx       |
##### 2. Answer the following questions:
◦ What type of cryptography is used by GnuPG?
R: Public key cryptography or asymmetric cryptography.
◦ What are the two main components of public key cryptography?
R: The public and the private keys.
◦ What is the KEY-ID of the public key fingerprint 07A6 5898 2D3A F3DD 43E3 DA95 1F3F 3147 FA7F 54C7?
R: FA7F 54C7
◦ What method is used to distribute public keys at a global level?
R Key servers.
##### 3. Put the following steps in the right order concerning private key revocation:
◦ Make the revoked key available to your correspondents.
◦ Create a revocation certificate.
◦ Import the revocation certificate to your keyring.
The correct order is:
Step 1: create a revocaion certificate
Step 2: import the revocation certificate to your keyring
Step 3: make the revoked jey avaiable to your correspondents
##### 4. Regarding file encryption, what does the --armor option imply in the command gpg --output encrypted-message --recipient carol --armor --encrypt unencrypted- message?
- R: It produces ASCII armored output, which allows you to copy the resulting existing encrypted file into an email.
# Explorational Exercises
##### 1. Most gpg options have both a long and a short version. Complete the table with the corresponding short version:

| Long version | Short version | Description                      |
| ------------ | ------------- | -------------------------------- |
| --armor      | -a            | Create ASCII armored output      |
| --output     | -o            | Write output to specified file   |
| --recipient  | -r            | Specify recipient for encryption |
| --decrypt    | -d            | Decrypt data                     |
| --encrypt    | -e            | Encrypt data                     |
| --sign       | -s            | Create digital signature         |
##### 2. Answer the following questions concerning key export:
◦ What command would you use to export all of your public keys to a file called all.key?
R: gpg --export --output all.key or gpg --export -o all.key
◦ What command would you use to export all of your private keys to a file called all_private.key?
 R: gpg --export-secret-keys --output all_private.key or gpg --export-secret -keys -o all_private.key (--export-secret-keys can be replaced by --export -secret-subkeys with a slightly different outcome — check man pgp for more information).
##### 3. What gpg option allows for carrying out most key management related tasks by presenting you with a menu?
- R: --edit-key
##### 4. What gpg option allows you to make a cleartext signature?
- R: --clearsign
- - - 
## ***Sources:***