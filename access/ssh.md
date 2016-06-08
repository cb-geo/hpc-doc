# SSH keys

SSH keys are a way to identify trusted computers without involving passwords. You can generate an SSH key and add the public key to Darwin by following the procedures outlined in this section. This section is based on the tutorials by [GitHub on using SSH keys](https://help.github.com/categories/ssh/)

## Checking for existing SSH keys

Before you generate an SSH key, you can check to see if you have any existing SSH keys.

* On a terminal do `ls -al ~/.ssh` to see if existing SSH keys are present:

* Check the directory listing to see if you already have a public SSH key.

By default, the filenames of the public keys are one of the following:

    id_dsa.pub
    id_ecdsa.pub
    id_ed25519.pub
    id_rsa.pub

## Creating a new SSH key

* On a terminal paste the text below, substituting in your email address.

    `ssh-keygen -t rsa -b 4096 -C "ab123@cam.ac.uk"`

Creates a new ssh key, using the provided email as a label generating public/private rsa key pair.

* When you're prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.

     `Enter a file in which to save the key (`/home/username/.ssh/id_rsa`): [Press enter]`

* At the prompt, type a secure passphrase.

     `Enter passphrase (empty for no passphrase): [Type a passphrase]`

     `Enter same passphrase again: [Type passphrase again]`

* This will generate two files a private key (`id_rsa`), keep this safe, and a public key `id_rsa.pub`. 


# Adding SSH key to the server
* Once the key pair is generated, the public key should be copied to the server (Darwin). 

* To copy your key from a terminal on your local machine:

  `ssh-copy-id -i ~/.ssh/id_rsa.pub ab123@login.hpc.cam.ac.uk`
 
  Alternatively, you can just use without the identity file, if your SSH key pair is called `id_rsa` by default:

  `ssh-copy-id ab123@login.hpc.cam.ac.uk`

> **Note** If you are on Mac, you may need to install `ssh-copy-id`. This can be done using the package manager for Mac, Brew. Install Brew [here](http://brew.sh/) and then simply type `brew install ssh-copy-id` in the command line.

* This will copy the public part of your SSH key pair to `~/.ssh/authorized_keys` on Darwin.

# Connecting to the server with SSH key
* Once you have copied the public part of your SSH key to the authorized keys file in Darwin's login node, you can connect to Darwin:

    `ssh ab123@login.hpc.cam.ac.uk`

or if you have a non-default name for your SSH key pair, then use:

    `ssh -i ~/.ssh/id_rsa ab123@login.hpc.cam.ac.uk`

