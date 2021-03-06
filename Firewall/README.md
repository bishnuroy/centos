##Firewall

Ref:  https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-using-firewalld-on-centos-7

**Firewalld is a complete firewall solution available by default on CentOS 7 and Redhat servers. 
In this guide, we will cover how to set up a firewall and the basics of managing the firewall with the firewall-cmd administrative tool**


##

**Stop Firewall**

    # service firewalld stop
    or
    #systemctl stop  firewalld.service
    
**Start Firewall**

    # service firewalld start
    or
    #systemctl start  firewalld.service
    
**Enable Firewall**
 
    # systemctl enable firewalld
    
**Disable Firewall**
 
        #systemctl disable firewalld
    


**We can verify that the service is running and reachable by typing:**

        #firewall-cmd --state
        
**We can see which zone is currently selected as the default by typing:**

        #firewall-cmd --get-default-zone
        
**We can print out the default zone's configuration by typing:**

        #firewall-cmd --list-all
        
**We can see the specific configuration associated with a zone by including the --zone= parameter in our --list-all command:**

        #firewall-cmd --zone=home --list-all
        
**We can transition our eth0 interface to the "home" zone by typing this:**

        #firewall-cmd --zone=home --change-interface=eth0
        
        
 **Opening a service for your Zones**
 
 
**We can allow http traffic for interfaces in our "public" zone for this session by typing:**
 
        #firewall-cmd --zone=public --add-service=http
        #firewall-cmd --zone=public --permanent --add-service=http
        
        #firewall-cmd --zone=publicweb --add-service=ssh
        #firewall-cmd --zone=publicweb --add-service=http
        #firewall-cmd --zone=publicweb --add-service=https
        
        #firewall-cmd --zone=public --permanent --list-services
        
**Opening a Port for Zones**

        #firewall-cmd --zone=public --permanent --add-port=80/tcp
        
        #firewall-cmd --zone=public --permanent --add-port=4990-4999/udp
        
        #firewall-cmd --zone=public --permanent --list-ports
        

**Creating Your Own Zones**

        #firewall-cmd --permanent --new-zone=publicweb
        #firewall-cmd --permanent --new-zone=privateDNS
        #firewall-cmd --permanent --get-zones
        
        
**Execute below command after change the firewall rulls**

        #firewall-cmd --reload
        #firewall-cmd --get-zones
