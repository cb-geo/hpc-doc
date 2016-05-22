## Linux or Mac OS 

Launch a terminal on Linux or Mac OS and connect to HPCS using SSH: `ssh ab123@login.hpc.cam.ac.uk`, where ab123 is your CRSid. More information on connecting to HPCS using SSH can be found [here](http://www.hpc.cam.ac.uk/using-clusters/connecting). If `SSH` is not installed, you might have to download and compile `OpenSSH`.

On your first SSH connection to the HPC service you will be presented with the current SSH public host key. 

This *fingerprint* MUST match either of these two values:

`0b:ef:59:90:fb:13:4a:c9:56:82:7b:cd:4b:2b:e1:3b`

or

`SHA256:sSkVfzpwjwiFvxLcdPoDpN8IsN3kt0ZSywhDhPKZPAg`

If this is not the case, there may be a security issue and you should contact [support@hpc.cam.ac.uk](mailto:support@hpc.cam.ac.uk) directly and as soon as possible. 