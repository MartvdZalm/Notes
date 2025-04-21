# CMD
### Fix permissions for the .ssh directory
chmod 700 ~/.ssh

### Fix permissions for the private key
chmod 600 ~/.ssh/id_rsa

### Fix permissions for the public key (optional)
chmod 644 ~/.ssh/id_rsa.pub

### Set Default Shell
chsh -s
