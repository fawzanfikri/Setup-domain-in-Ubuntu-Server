# Setup-domain-in-Ubuntu-Server

# How to setup Web on Ubuntu Server
1. Make sure Ubuntu have Apache Service.
2. Make a folder in /var/www/ using `sudo mkdir foldername`
3. Run `cd /etc/apache2/sites-available/`
4. Run `cp 000-default.conf domainname` 
5. Run `sudo nano domainname` to edit the virtualhost
6.  Change to the configuration below:

 `<VirtualHost *:80>`
 
        `ServerName www.domainname.test #main name`
        
        `ServerAlias domainname.test  #second name` 
        
        `ServerAdmin webmaster@localhost`
        
        `DocumentRoot /var/www/foldername/`
        
        `ErrorLog ${APACHE_LOG_DIR}/error.log`
        
        `CustomLog ${APACHE_LOG_DIR}/access.log combined`
        
 `</VirtualHost>`
 
7. Run `sudo a2ensite domainname` 
8. Run `sudo systemctl restart apache2`
9. Type domainname.test in your browser.
