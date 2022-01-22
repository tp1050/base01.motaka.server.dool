Challenges:

1. Permanence:
2. Write permission
3. Reconnects 
4. Authentication


Install ssh:
`sudo apt install ssh sshfs`

generate SSH Keys:

`mkdir $HOME/.ssh`
`chmod 0700 $HOME/.ssh`
`cd $HOME/.ssh`


`ssh-keygen -t rsa 4096`

copy the keys to the server
`ssh-copy-id username@remotehost`



##Do not recommend it
#Disable Password Authentication on the:
#`sudo nano /etc/ssh/sshd_config`
#change 
#`PasswordAuthentication no`

`sudo systemctl restart ssh`

##Challenges are how to get around default read_only
#1) The mounted folder can only viewed using `su` and graphically must run graphical su equivalent

`sudo sshfs user@remote:/home/user/ /home/userc/1/2 -o reconnect -o idmap=user -o allow_other -o allow_root`
