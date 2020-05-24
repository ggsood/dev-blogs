# Accessing Remote Machines Using SSH

### SSH Keys
One of the main advantages to using SSH are SSH keys. They are a cryptographic public/private key pair used for authentication. 

They always come in twos. The private key is stored on the client. The public key is stored on the remote machine.
When a user makes an attempt to connect to a remote machine via SSH, the protocol will check the user’s computer for the private key that matches the public key stored on the remote machine. If there is a match, the connection is successful. No password needed! You can even add a passphrase for added security.

### How to setup SSH keys

**Step 1: Generate SSH Keys**

`ssh-keygen -t rsa`

**Step 2: Name your SSH keys**

After entering the command, you should get this output:
```
Generating public/private rsa key pair. 
Enter file in which to save the key(/Users/<local_user>/.ssh/id_rsa)
```

`<local_user>`  refers to your local computer's current user.

The terminal instructs us to enter the name of a file in which we want our private key to be saved. 

You have 2 options:

a. Choose the default filename id_rsa

b. Provide your own unique filename

Two important things to note here:

If you plan on having multiple SSH keys, it’s best to name each one uniquely.

If you decide to provide a unique filename, you must type in the complete file path along with the filename.

Recommend to add a unique word after id_rsa that describes which remote machine the key will be used to connect to.

**Step 3: Enter a passphrase (optional)**

For added security over ssh.

**Step 4: Move the public key to the remote machine**

The public key has to be placed on whatever remote machine you plan on accessing via SSH.

In your terminal, enter:
```
ssh-copy-id -i ~/.ssh/<public_key_file> <user>@<remote machine>
```
ssh-copy-id moves the public key file specified with -i ~/.ssh/<public_key_file> 

**Step 5: Test your connection**

Go ahead and attempt to login to the remote machine using:
`ssh <user>@<remote machine>`