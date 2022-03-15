# datapower-guide

## Create HTTPS  
  
  1. Create Crypto Key. Go to menu **Crypto Tools** and create the keys. Fill up the fields and turn on the **Export Private Key** option.  
  To verify the exported file, go to menu **File Management**. Expand the temporary: directory. Notice the exported private key, the self-signed certificate, and the CSR.  
    
  2. Create Crypto Objects. Go to menu **"Crypto Identification Credentials"**, on the Configure Crypto Identification Credentials page, click New.  
     Choose the just created key and certificate in step 1. Leave intermediate CA blank.  
     
  3. Create a validation credential object, go to menu **Crypto Validation Credentials**.  
     A validation credential object is used to validate the authenticity of certificates and digital signatures that is presented to a service.  
     Add the certificate and leave the other options as default.  
     
  4. Create a server crypto profile to use in an SSL communication. Go to menu **Crypto Profile**.
     A crypto profile is used to identify certificate-key pairs in an SSL connection. It can also validate presented certificates by using a validation credential object.  
     Enter the CryptoID and CryptoValCred created in the earlier steps. Uncheck disable SSL version 3.  
     
  5. Apply the crypto profile to an HTTPS port  
  6. Test the SSL from http://<image_ip>/dp/searchConfig.html  

## Install Datapower on Linux
  
  1. Download the installer from Passport Advantage
  2. Extract the downloaded file on the server 
  3. Install Epel-release
```
yum install epel-release
```
  4. Install Datapower rpm 
```
yum install xxx.image.x86_64.rpm xxx.common.x86_64.rpm --nogpgcheck
```
  5. Start Datapower service
```
systemctl start datapower
```
  6. Configure the web management services
```
telnet 127.0.0.1 2200
```
  7. Login with default username/password: admin/admin, assign new password
  8. Setup the web management interface with the following command
```
configure terminal;web-mgmt;admin-state enabled;local-address 0 9090;exit
```
  9. Access the web management interface at https://[your-server-ip]:9090/dp



     
     
     
