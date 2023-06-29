
Assemble Hardware: 
Rasberry Pi 4 - 8GB Ram
Case
1TB Drive
64GB MicroSD Card

Software: 
* Use functioning computer ... will use personal desktop
* Set up SSH (~/.ssh/authorized_keys)
    - Use Terminal on Mac OS
    - Use Putty on Windows
* Advanced Options: Set public-key authentication for SSH using Putty
    - Use Rasberry Imager to install Rasberry Pi OS


To Generate SSH Key on Mac OS, use the command 'ssh-keygen -t ed25519 -C "Rasberry Pi NEW"' to generate a public/private key pair:
    flags:  -t ed25519 #type of key to be created i.e. ed25519
            -C "A comment (or name) to help identify keys among keys"
 ... should store file it in folder: ~/.ssh/
No passphrase is okay on personal machine
2 files will be created, 1 is *.pub (public) & the other private. 
A fingerprint will be created;  

copy ssh keys by command: 'pbcopy < ~/.ssh/[PUBLIC_KEY_FILE].pub' #COPY PUBLIC SSH KEY TO CLIPBOARD
paste keys into advanced option dialog in imager; 

sudo lsblk -o UUID,NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL #to list connect external drive characteristics; 

/dev/sda: UUID="***" BLOCK_SIZE="4096" TYPE="ext4"
UUID=*** /mnt/drive ext4 defaults,auto,users,rw,nofail,noatime 0 0

sudo install --verbose --owner=root --group=root --mode=0755 --target-directory=/usr/local/bin ~/bitcoin-22.0/bin/*

sudo install --verbose --owner=**** --target-directory=/usr/local/bin ~/bitcoin-0.22.0/bin/*
