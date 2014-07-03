# SSH

**Copy SSH key to server for SSH connection via key authentification**

Option1: copy manualy

Start on the Server you want to reach

	sudo mkdir -p /home/$USER/.ssh
	sudo nano /home/$USER/.ssh/authorized_key #copy your public key into file
	sudo chown -R $USER:$USERGROUP /home/$USER
	sudo chmod 700 /home/$USER/.ssh
	sudo chmod 600 /home/$USER/.ssh/authorized_key

Option2: ssh-copy-id

Start from your local Machine

	ssh-copy-id $USER@$SERVER

**Disable login via password authentification**

	sudo nano /etc/ssh/sshd_config

Ensure that following variables are set

	PasswordAuthentication no
	RSAAuthentication yes
	PubkeyAuthentication yes

Reload Service to load the changes

	sudo /etc/init.d/sshd reload
