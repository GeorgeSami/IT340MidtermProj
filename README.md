# IT340MidtermProj
Content Delivery Network Deliverables 

1- Install  a) Apache2.
            b) MySQL.
            c) PHP5.
            d) FTP.

2- Configure a user to work with FTP with a file Quota

3- Configure Nagios to Monitor the user's disk usage.

4- Configure Nagios to Monitor Apache2 availability.

==========================================================

1- Installing  
a) Apache2:

>> sudo apt-get install apache2


b) MySQL:

>> sudo apt-get install mysql-server
- to activate MySQL
>> sudo mysql_install_db
- to run MySQL setup script:
>> sudo /user/bin/mysql_secure_installation


c) PHP5:

>> sudo apt-get install php5 libapache2-mod-php5
- to use MySQL with PHP5
>> sudo apt-get install php5-mysql


d) FTP: 

>> sudo apt-get install vsftpd


====

2- Configure a user to work with FRP with a file quota:

>> sudo apt-get install quota
>> sudo nano /etc/fstab
- added the following line to fstab:
>> /dev/sda1 / ext4 defaults,usrquota 1 1
- remount
>> mount -vo remount /
- to enable quota:
>> quotaon -av
- edited quota for user (george) using the following line:
>> edquota george
set soft limit to 90000 and hard limit to 100000
>>quotacheck -vgum


========

3- Configure Nagios to Monitor the user's disk usage:

>> sudo apt-get install nagios3 nagios-nrpe-plugin
please see: /etc/nagios3/conf.d/george.cfg

=======

4- Configure Nagios to Monitor Apache2 availability:

Please see: /etc/nagios3/conf.d/services_nagios2.txt
