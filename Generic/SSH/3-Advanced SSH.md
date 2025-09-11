## **Tunneling and Port Forwarding**
- Local Port Forwarding:
``` bash
ssh -L 8080:localhost:80 user@remote_host
```

- Remote Port Forwarding:

``` bash
ssh -R 9090:localhost:22 user@remote_host
```

- Dynamic SOCKS Proxy:
``` bash
ssh -D 8080 user@remote_host
```


## **Copying Files with SCP**
 - Copy file to remote server:    
``` bash
scp file.txt user@remote_host:/path/to/destination
scp -p 2222 /local-files user@ip-address:remote-files
scp -p 2222 /opt/test user@ip:~/Download
```
  
  - Copy file from remote server:
``` bash
scp user@remote_host:/path/to/file.txt .
```


- **Using SFTP for Secure File Transfer**
    - Connect to remote SFTP:
``` bash
sftp user@remote_host
```
    - Download a file:

``` bash
get remote_file
```

    - Upload a file:
``` bash
put local_file
```


- **SSH Multiplexing for Faster Connections**
``` bash
echo "
Host *     
ControlMaster auto
ControlPath ~/.ssh/sockets/%r@%h-%p
ControlPersist 10m" >> ~/.ssh/config
```

- **SSH Escape Sequences (while connected)**
    - Suspend SSH session: `~^Z`
    - Kill hung session: `~.`

### **6. Securing SSH Server**

- Changing the default SSH port:
``` bash
sudo nano /etc/ssh/sshd_config 
# Change: Port 22 → Port 2222 
sudo systemctl restart ssh
```


- Disabling root login:
``` bash
PermitRootLogin no
```

- Limiting users:
``` bash
AllowUsers user1 user2
```

- Using Fail2Ban to prevent brute-force attacks:
``` bash
sudo apt install fail2ban 
sudo systemctl enable fail2ban
```

### **7. Troubleshooting SSH Issues**

- Checking SSH logs:
``` bash
journalctl -u ssh --no-pager | tail -n 20
```

- Debugging SSH connection:
``` bash
ssh -vvv user@remote_host
```