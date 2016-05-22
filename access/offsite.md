## Off-site access to HPCS

The HPCS is accessible only within Cambridge University Data Network. In order to access HPCS you need to first connect to a CUDN machine, for example the MCS cluster (`linux.pwf.cam.ac.uk`) or the CUED Gateway (`gate.eng.cam.ac.uk`).

## Accessing HPCS - VPN

Virtual Private Network (VPN) allows users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network (in this case CUDN). University of Cambridge offers a free VPN service, more information can be found [here](http://www.ucs.cam.ac.uk/vpn). Researchers at the CUED can request for an engineering department's [VPN](http://www-h.eng.cam.ac.uk/help/network/vpn/). Once connected to a VPN, you can access the HPCS as usual. This is the most straightforward method for accessing the HPC off-site.

## Accessing HPCS - SSH tunneling

Port forwarding via SSH (SSH tunneling) creates a secure connection between a local computer and a remote machine through which services can be relayed. In this section we will use `gate.eng.cam.ac.uk` to relay services. Alternatively, `linux.pwf.cam.ac.uk` can also be used.

### Windows (MobaXterm)

* Create an `SSH` session, select `Session` and choose `SSH` in the `Session settings`. 

* Set remote host as `login.hpc.cam.ac.uk`, tick `Specify username` and type your CRSid in the box provided. Leave the port to be `22` and click `OK`.

![Setting up SSH using MobaXterm](mobaxterm-ssh.png)

* Select `Network Settings` tab. Toggle on `Connect through SSH gateway (jump host)`. 

* Set `Gateway SSH server` to `gate.eng.cam.ac.uk`, port as `22` and User `ab123` (CRSid). Select OK.

![Off-site access using MobaXterm](mobaxterm-offsite.png)

* Launch the session from Session tab. This will prompt you for `gate.eng.cam.ac.uk` password. 

* This will be followed by another prompt `ab123@127.0.0.1`, this is HPCS forwarded to `gate.eng.cam.ac.uk`. Please enter your RAVEN password to login to HPCS.

### Linux or MacOS

One method to login to HPCS is to first login to an intermediary server (`gate.eng.cam.ac.uk` or `linux.pwf.cam.ac.uk`) and then ssh to HPCS. See previous section on SSH Linux. Alternatively, you can run
do this using a single command:

* Launch a terminal and type `ssh -tt ab123@gate.eng.cam.ac.uk ssh -tt ab123@login.hpc.cam.ac.uk`.

* This will prompt password for `gate.eng.cam.ac.uk` followed by the password prompt for HPCS.

