- **Tunneling and Port Forwarding**
    - Local Port Forwarding:
        
        bash
        
        CopyEdit
        
        `ssh -L 8080:localhost:80 user@remote_host`
        
    - Remote Port Forwarding:
        
        bash
        
        CopyEdit
        
        `ssh -R 9090:localhost:22 user@remote_host`
        
    - Dynamic SOCKS Proxy:
        
        bash
        
        CopyEdit
        
        `ssh -D 8080 user@remote_host`
        
- **Copying Files with SCP**
    - Copy file to remote server:
        
        bash
        
        CopyEdit
        
        `scp file.txt user@remote_host:/path/to/destination`
        
    - Copy file from remote server:
        
        bash
        
        CopyEdit
        
        `scp user@remote_host:/path/to/file.txt .`
        
- **Using SFTP for Secure File Transfer**
    - Connect to remote SFTP:
        
        bash
        
        CopyEdit
        
        `sftp user@remote_host`
        
    - Download a file:
        
        bash
        
        CopyEdit
        
        `get remote_file`
        
    - Upload a file:
        
        bash
        
        CopyEdit
        
        `put local_file`
        
- **SSH Multiplexing for Faster Connections**
    
    bash
    
    CopyEdit
    
    `echo "Host *     ControlMaster auto     ControlPath ~/.ssh/sockets/%r@%h-%p     ControlPersist 10m" >> ~/.ssh/config`
    
- **SSH Escape Sequences (while connected)**
    - Suspend SSH session: `~^Z`
    - Kill hung session: `~.`

### **6. Securing SSH Server**

- Changing the default SSH port:
    
    bash
    
    CopyEdit
    
    `sudo nano /etc/ssh/sshd_config # Change: Port 22 → Port 2222 sudo systemctl restart ssh`
    
- Disabling root login:
    
    bash
    
    CopyEdit
    
    `PermitRootLogin no`
    
- Limiting users:
    
    bash
    
    CopyEdit
    
    `AllowUsers user1 user2`
    
- Using Fail2Ban to prevent brute-force attacks:
    
    bash
    
    CopyEdit
    
    `sudo apt install fail2ban sudo systemctl enable fail2ban`
    

### **7. Troubleshooting SSH Issues**

- Checking SSH logs:
    
    bash
    
    CopyEdit
    
    `journalctl -u ssh --no-pager | tail -n 20`
    
- Debugging SSH connection:
    
    bash
    
    CopyEdit
    
    `ssh -vvv user@remote_host`