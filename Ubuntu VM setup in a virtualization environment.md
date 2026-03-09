# Download Ubuntu to desktop
    https://ubuntu.com/download/desktop

# Open your Virtual machine and Add Ubuntu ISO file
- Watch full video on how to do this here:

# Set IP to Static
    
<img width="1276" height="781" alt="ubuntu set static" src="https://github.com/user-attachments/assets/c23b23d4-e685-451f-882f-7c9c114829eb" />
      
# Open terminal on ubuntu and install update
        sudo apt update
        (put in your OS password, if required)
        sudo apt upgrade -y

# Install dependencies
    sudo apt install -y python3-dev python3-venv python3-pip mariadb-server mariadb-client redis-server curl git nodejs npm
    sudo npm install -g yarn

# Configure MariaDB
- Frappe requires specific database settings. Edit the configuration file:    

        sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
  
- write this in the file:
  
        innodb-check-optimize-description = OFF
        innodb-adaptive-hash-index = OFF
        character-set-client-handshake = FALSE
        character-set-server = utf8mb4
        collation-server = utf8mb4_unicode_ci
- Restart MariaDB:

      sudo service mysql restart
