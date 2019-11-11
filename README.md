# PrinterScanner

sudo apt-get install cups
sudo vim /etc/cups/cupsd.conf

Port 631
DefaultEncryption Never
DefaultAuthType None 

 . . . .

<Location />
  Order allow,deny
  Allow from all
</Location>
<Location /admin>
  Order allow,deny
  Allow from all
</Location>
<Location /admin/conf>
  AuthType Default
  Require user @SYSTEM
  Order deny,allow
  Allow from all
</Location>


service cups restart
