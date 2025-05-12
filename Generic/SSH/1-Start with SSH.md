- Installing OpenSSH on different Linux distributions:
    
    bash
    
    CopyEdit
    
    `sudo apt install openssh-server  # Debian/Ubuntu sudo dnf install openssh-server  # Fedora/RHEL sudo pacman -S openssh           # Arch Linux`
    
- Starting, stopping, and enabling SSH service:
    
    bash
    
    CopyEdit
    
    `sudo systemctl start ssh sudo systemctl enable ssh sudo systemctl status ssh`
    
- Configuring SSH (editing `/etc/ssh/sshd_config`)
- Restarting SSH after changes:
    
    bash
    
    CopyEdit
    
    `sudo systemctl restart ssh`
    
- Checking SSH listening ports:
    
    bash
    
    CopyEdit
    
    `netstat -tlnp | grep ssh`
    

### **3. Connecting to Remote Servers using SSH**

- Basic SSH command:
    
    bash
    
    CopyEdit
    
    `ssh user@remote_host`
    
- Specifying a port:
    
    bash
    
    CopyEdit
    
    `ssh -p 2222 user@remote_host`
    
- Connecting with an identity file:
    
    bash
    
    CopyEdit
    
    `ssh -i ~/.ssh/id_rsa user@remote_host`
    
- Running a command remotely:
    
    bash
    
    CopyEdit
    
    `ssh user@remote_host "ls -la"`
    

### **4. Managing SSH Keys for Authentication**

- Generating SSH key pairs:
    
    bash
    
    CopyEdit
    
    `ssh-keygen -t rsa -b 4096`
    
- Adding a public key to the remote server:
    
    bash
    
    CopyEdit
    
    `ssh-copy-id user@remote_host`
    
- Manually adding keys:
    
    bash
    
    CopyEdit
    
    `cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`
    
- Using SSH agent to manage keys:
    
    bash
    
    CopyEdit
    
    `eval "$(ssh-agent -s)" ssh-add ~/.ssh/id_rsa`