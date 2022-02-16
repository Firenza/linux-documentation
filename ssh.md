1. Generate your keys `ssh-keygen -t rsa`
1. Store the key in `/Users/YOUR_USERNAME/.ssh/id_rsa_NEW_DEVICE_NAME`
1. Copy the public key to the new device `ssh-copy-id -i ~/.ssh/id_rsa_NEW_DEVICE_NAME.pub user@server`
1. Go into the server ssh config file and turn on public key auth and turn off password auth
    1. `sudo nano /etc/ssh/sshd_config`
    1. Turn on public key auth `PubkeyAuthentication yes`
    1. Turn off password auth `PasswordAuthentication no`
    1. Restart ssh server `sudo systemctl restart sshd`
1. Go into client ssh config file and map a host to a user and key file
    1. Open file `nano ~/.ssh/config`
    1. Add new host entry
        ```bash
        Host YOUR_HOST_NAME
            IdentityFile /Users/YOUR_USERNAME/.ssh/id_rsa_NEW_DEVICE_NAME
            User YOUR_USER_NAME
        ```