


Steps1:

    Install httpd.
    
        => yum install httpd -y
    
Step2:

    Install httpd-tools.
        
        => yum install httpd-tools -y


Step3:

    Install mod_ldap module.
    
        => yum install mod_ldap -y

Now create "*.config" file in "/etc/httpd/conf.d/" this path.


Sample file as below.

https://github.ibm.com/CIOCloud/bfringe_logging/blob/restructure/Platforms/http-url-auth/bfcdhnn301.conf


        NB: For different Listening port (Listen 50070) have to create different *.config file.
  
Step4:

    Now restart the httpd service.
    
            => systemctl restart httpd
