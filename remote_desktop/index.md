# Remote desktop

A VNC server is a program that shares a desktop with other computers over the Internet. SSH to a login node and for the first time launch a vncserver session. For 3D graphics session and visualisation of results using `ParaView` use `login-gfx1`.

* Run `vncserver` command to create a remote desktop. When prompted set a password to access your desktop.

> **Note** VNC server password length should not be more than 8 characters

* A remote desktop session will be created on display `X`. For example, `login-sand2:8` where the display session number is `8`.

* To find the display in which a remote desktop server is already runny, please use the command `vncserver -list`. 

* To kill an existing remote destop session do: `vncserver -kill :X`, where `X` is the display session number.

## Windows (MobaXterm)

## Linux

* In order to connect to a VNC server from your machine, ensure you have a vnc viewer client installed, for example tiger vnc viewer.

* To connect to an existing remote desktop session, run
`vncviewer -via ab123@login-sandNN.hpc.cam.ac.uk localhost:X`, where `ab123` is the CRSid, `NN` refers to the login node and `X` is the display session number. To connect to `login-sand2:8`, the command will be `vncviewer -via ab123@login-sand2.hpc.cam.ac.uk localhost:8`
