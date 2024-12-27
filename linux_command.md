# Automatically started services
``systemctl list-unit-files --type=service --state=enabled`` - to check which services start when boot  
``sudo systemctl disable <service_name>`` - to stop a service  

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
**htop** - for cpu usage  
**iotop** - for disk usage  
**lsblk** - to list the name of the partition  
**lscpu** - cpu specifications  

# OS scheduling
``cat /sys/block/sda/queue/scheduler`` - to know which scheduling is used by the pc (ususlly mq-deadline or bfq)  
``echo mq-deadline | sudo tee /sys/block/sda/queue/scheduler`` - to change the scheduling  



