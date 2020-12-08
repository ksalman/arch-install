# Basic Arch install
## Prepare the host/VM for ansible
1. Set the root password with ``passwd``
2. Use vim to edit the file /etc/ssh/sshd_config by changing the ChallengeResponseAuthentication setting to yes.
3. Restart the ssh service using systemctl restart sshd.
4. Create a keyfile on your local host containing the password for your LUKS root volume via ``echo -n "your_password" > keyfile``.

# Deploy
The following will try to run on all the hosts in inventory.yaml
```ansible-playbook -i inventory.yaml site.yaml``` -u root
One can also specify a comma separated list of hosts, note the comma
```ansible-playbook -i 192.168.1.95, site.yaml``` -u root

# Notes
At bootloader screen, add ``cow_spacesize=5G`` so the root filesystem is 5G
