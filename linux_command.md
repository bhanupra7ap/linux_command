# Automatically started services
``systemctl list-unit-files --type=service --state=enabled`` - to check which services start when boot  
``sudo systemctl disable <service_name>`` - to stop a service  

# Background Process
``screen -S session_namee`` - creates seperate screen in background
**Press Ctrl + A, then D to detach from the screen and run in background**
``screen -r session_name`` - to reconnect with the screen
``screen -ls`` - list all the screen running
``screen -X -S session_name quit`` - to terminate screen
**OR reconnect with the screen and type "exit"** 

# Disk Formatting
``sudo shred -v -n 3 -z /dev/sdX`` - overwrites the disk sdX 3 times(-n) to make the data unrecoverable
``sudo dd if=/dev/zero of=/dev/sdX bs=1M status=progress`` - fills the disk sdX with zeros
``sudo dd if=/dev/urandom of=/dev/sdX bs=1M status=progress`` - fills the disk sdX with random data

# Disk health check
### system status check ( or long test results)
``sudo smartctl -l selftest /dev/sda``
### long test
``sudo smartctl -t long /dev/sda`` - for detailed check
### mark bad sectors as unusable
``sudo badblocks -v /dev/sda > badblocks.log`` - checks for bad blocks with verbose (tells the result) saving the results in a file named badblocks.log  
**OR** ``sudo badblocks -n /dev/sda`` - checks without destructing existing data  
**OR** ``sudo badblocks -w /dev/sda`` - destructs existing data while checking (only for unmounted or unused disk)  


``sudo e2fsck -l badblocks.log /dev/sda1`` - inform filesystems about the bad blocks  

# Firewall
### Enable/Disable/Reset UFW
``sudo ufw enable/disable/reset``
### Check current rules
``sudo ufw status``
### Allow/Deny a specific port
``sudo ufw allow/deny <port>``
### Allow a specific service
``sudo ufw allow <service_name>``

# GitHub
``ssh-keygen -t rsa -b 4096 -C "email@example.com"`` - create new ssh key  
``cat ~/.ssh/id_rsa.pub`` - read the public key  

### for large files:
``git lfs track *``  
``git add .gitattributes``  
``git add .``  
``git commit -m "message"``  
``git push``  

# Hardware specs
``htop`` - for cpu usage  
``iotop`` - for disk usage  
``lsblk`` - to list the name of the partition  
``lscpu`` - cpu specifications  

# OS scheduling
``cat /sys/block/sda/queue/scheduler`` - to know which scheduling is used by the pc (ususlly mq-deadline or bfq)  
``echo mq-deadline | sudo tee /sys/block/sda/queue/scheduler`` - to change the scheduling  



