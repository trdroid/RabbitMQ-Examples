### Installation

Erlang should be installed prior to the installation of RabbitMQ.

```sh
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ ls
rabbitmq-server_3.6.6-1_all.deb
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo dpkg -i rabbitmq-server_3.6.6-1_all.deb 
[sudo] password for droid: 
(Reading database ... 750716 files and directories currently installed.)
Preparing to unpack rabbitmq-server_3.6.6-1_all.deb ...
Unpacking rabbitmq-server (3.6.6-1) over (3.6.6-1) ...
dpkg: dependency problems prevent configuration of rabbitmq-server:
 rabbitmq-server depends on erlang-nox (>= 1:16.b.3) | esl-erlang; however:
  Package erlang-nox is not installed.
  Package esl-erlang is not installed.
 rabbitmq-server depends on socat; however:
  Package socat is not installed.

dpkg: error processing package rabbitmq-server (--install):
 dependency problems - leaving unconfigured
Processing triggers for man-db (2.6.7.1-1ubuntu1) ...
Processing triggers for ureadahead (0.100.0-16) ...
ureadahead will be reprofiled on next reboot
Errors were encountered while processing:
 rabbitmq-server
```

https://www.howtoinstall.co/en/ubuntu/trusty/erlang-nox

```sh
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo apt-get install erlang-nox
Reading package lists... Done
Building dependency tree       
Reading state information... Done
You might want to run 'apt-get -f install' to correct these:
The following packages have unmet dependencies:
 erlang-nox : Depends: erlang-base but it is not going to be installed or
                       erlang-base-hipe but it is not going to be installed
              Depends: erlang-asn1 but it is not going to be installed
              Depends: erlang-corba but it is not going to be installed
              Depends: erlang-crypto but it is not going to be installed
              Depends: erlang-diameter but it is not going to be installed
              Depends: erlang-edoc but it is not going to be installed
              Depends: erlang-eldap but it is not going to be installed
              Depends: erlang-erl-docgen but it is not going to be installed
              Depends: erlang-eunit but it is not going to be installed
              Depends: erlang-ic but it is not going to be installed
              Depends: erlang-inets but it is not going to be installed
              Depends: erlang-mnesia but it is not going to be installed
              Depends: erlang-odbc but it is not going to be installed
              Depends: erlang-os-mon but it is not going to be installed
              Depends: erlang-parsetools but it is not going to be installed
              Depends: erlang-percept but it is not going to be installed
              Depends: erlang-public-key but it is not going to be installed
              Depends: erlang-runtime-tools but it is not going to be installed
              Depends: erlang-snmp but it is not going to be installed
              Depends: erlang-ssh but it is not going to be installed
              Depends: erlang-ssl but it is not going to be installed
              Depends: erlang-syntax-tools but it is not going to be installed
              Depends: erlang-tools but it is not going to be installed
              Depends: erlang-webtool but it is not going to be installed
              Depends: erlang-xmerl but it is not going to be installed
 rabbitmq-server : Depends: socat but it is not going to be installed
E: Unmet dependencies. Try 'apt-get -f install' with no packages (or specify a solution).
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo apt-get update
Get:1 http://security.ubuntu.com trusty-security InRelease [65.9 kB]
Ign http://dl.google.com stable InRelease                                      
Ign http://dl.google.com stable InRelease                                      
Hit http://apt.postgresql.org trusty-pgdg InRelease                            
Hit http://dl.google.com stable Release.gpg                                    
Ign http://repo.mongodb.org trusty/mongodb-org/3.2 InRelease                   
Ign http://extras.ubuntu.com trusty InRelease                                  
Ign http://ca.archive.ubuntu.com trusty InRelease                              
Hit http://repo.mongodb.org trusty/mongodb-org/3.2 Release.gpg                 
Ign http://www.openprinting.org lsb3.2 InRelease                               
Hit http://dl.google.com stable Release.gpg                                    
Hit http://ppa.launchpad.net trusty InRelease                                  
Ign http://toolbelt.heroku.com ./ InRelease                                    
Get:2 http://extras.ubuntu.com trusty Release.gpg [72 B]                       
Get:3 http://security.ubuntu.com trusty-security/main Sources [122 kB]         
Hit http://dl.google.com stable Release                                        
Hit http://repo.mongodb.org trusty/mongodb-org/3.2 Release                     
Hit http://www.openprinting.org lsb3.2 Release.gpg                             
Get:4 http://ca.archive.ubuntu.com trusty-updates InRelease [65.9 kB]          
Hit http://toolbelt.heroku.com ./ Release.gpg                                  
Hit http://ppa.launchpad.net trusty InRelease                                  
Hit http://dl.google.com stable Release                                        
Hit http://extras.ubuntu.com trusty Release                                    
Hit http://apt.postgresql.org trusty-pgdg/main amd64 Packages                  
Hit http://www.openprinting.org lsb3.2 Release                                 
Hit http://dl.google.com stable/main amd64 Packages                            
Hit http://toolbelt.heroku.com ./ Release                                      
Get:5 http://security.ubuntu.com trusty-security/restricted Sources [4,613 B]  
Hit http://ppa.launchpad.net trusty/main amd64 Packages                        
Hit http://repo.mongodb.org trusty/mongodb-org/3.2/multiverse amd64 Packages   
Get:6 http://security.ubuntu.com trusty-security/universe Sources [45.8 kB]    
Hit http://apt.postgresql.org trusty-pgdg/main i386 Packages                   
Hit http://ppa.launchpad.net trusty/main i386 Packages                         
Get:7 http://security.ubuntu.com trusty-security/multiverse Sources [3,207 B]  
Hit http://extras.ubuntu.com trusty/main Sources                               
Hit http://dl.google.com stable/main amd64 Packages                            
Hit http://www.openprinting.org lsb3.2/main amd64 Packages                     
Get:8 http://security.ubuntu.com trusty-security/main amd64 Packages [556 kB]  
Hit http://toolbelt.heroku.com ./ Packages                                     
Hit http://ca.archive.ubuntu.com trusty-backports InRelease                    
Hit http://ppa.launchpad.net trusty/main Translation-en                        
Hit http://extras.ubuntu.com trusty/main amd64 Packages                        
Hit http://www.openprinting.org lsb3.2/main i386 Packages                      
Hit https://apt.dockerproject.org ubuntu-trusty InRelease                      
Hit http://ppa.launchpad.net trusty/main amd64 Packages                        
Hit http://ca.archive.ubuntu.com trusty Release.gpg                            
Hit https://apt.dockerproject.org ubuntu-trusty/main amd64 Packages            
Hit http://extras.ubuntu.com trusty/main i386 Packages                         
Get:9 https://apt.dockerproject.org ubuntu-trusty/main Translation-en_CA       
Hit http://ppa.launchpad.net trusty/main i386 Packages                         
Get:10 http://ca.archive.ubuntu.com trusty-updates/main Sources [385 kB]       
Hit http://ppa.launchpad.net trusty/main Translation-en                        
Get:11 http://security.ubuntu.com trusty-security/restricted amd64 Packages [13.3 kB]
Get:12 http://security.ubuntu.com trusty-security/universe amd64 Packages [144 kB]
Ign http://apt.postgresql.org trusty-pgdg/main Translation-en_CA               
Ign http://toolbelt.heroku.com ./ Translation-en_CA                            
Get:13 http://security.ubuntu.com trusty-security/multiverse amd64 Packages [4,138 B]
Ign http://toolbelt.heroku.com ./ Translation-en                               
Get:14 http://ca.archive.ubuntu.com trusty-updates/restricted Sources [5,888 B]
Get:15 http://security.ubuntu.com trusty-security/main i386 Packages [516 kB]  
Ign http://apt.postgresql.org trusty-pgdg/main Translation-en                  
Ign https://apt.dockerproject.org ubuntu-trusty/main Translation-en_CA         
Ign https://apt.dockerproject.org ubuntu-trusty/main Translation-en            
Ign http://dl.google.com stable/main Translation-en_CA                         
Hit http://repo.mongodb.org trusty/mongodb-org/3.2/multiverse i386 Packages    
Get:16 http://ca.archive.ubuntu.com trusty-updates/universe Sources [169 kB]   
Ign http://dl.google.com stable/main Translation-en                            
Ign http://dl.google.com stable/main Translation-en_CA                         
Get:17 http://security.ubuntu.com trusty-security/restricted i386 Packages [13.1 kB]
Ign http://dl.google.com stable/main Translation-en                            
Get:18 http://security.ubuntu.com trusty-security/universe i386 Packages [144 kB]
Get:19 http://ca.archive.ubuntu.com trusty-updates/multiverse Sources [7,522 B]
Get:20 http://security.ubuntu.com trusty-security/multiverse i386 Packages [4,289 B]
Get:21 http://ca.archive.ubuntu.com trusty-updates/main amd64 Packages [919 kB]
Hit http://security.ubuntu.com trusty-security/main Translation-en             
Hit http://security.ubuntu.com trusty-security/multiverse Translation-en       
Hit http://security.ubuntu.com trusty-security/restricted Translation-en       
Hit http://security.ubuntu.com trusty-security/universe Translation-en         
Ign http://extras.ubuntu.com trusty/main Translation-en_CA                     
Ign http://extras.ubuntu.com trusty/main Translation-en                        
Ign http://www.openprinting.org lsb3.2/main Translation-en_CA                  
Hit http://www.openprinting.org lsb3.2/main Translation-en                     
Ign http://repo.mongodb.org trusty/mongodb-org/3.2/multiverse Translation-en_CA
Ign http://repo.mongodb.org trusty/mongodb-org/3.2/multiverse Translation-en
Get:22 http://ca.archive.ubuntu.com trusty-updates/restricted amd64 Packages [16.4 kB]
Get:23 http://ca.archive.ubuntu.com trusty-updates/universe amd64 Packages [388 kB]
Get:24 http://ca.archive.ubuntu.com trusty-updates/multiverse amd64 Packages [14.0 kB]
Get:25 http://ca.archive.ubuntu.com trusty-updates/main i386 Packages [880 kB]
Get:26 http://ca.archive.ubuntu.com trusty-updates/restricted i386 Packages [16.2 kB]
Get:27 http://ca.archive.ubuntu.com trusty-updates/universe i386 Packages [389 kB]
Get:28 http://ca.archive.ubuntu.com trusty-updates/multiverse i386 Packages [14.5 kB]
Get:29 http://ca.archive.ubuntu.com trusty-updates/main Translation-en [445 kB]
Get:30 http://ca.archive.ubuntu.com trusty-updates/multiverse Translation-en [7,340 B]
Get:31 http://ca.archive.ubuntu.com trusty-updates/restricted Translation-en [3,842 B]
Get:32 http://ca.archive.ubuntu.com trusty-updates/universe Translation-en [205 kB]
Hit http://ca.archive.ubuntu.com trusty-backports/main Sources                 
Hit http://ca.archive.ubuntu.com trusty-backports/restricted Sources           
Hit http://ca.archive.ubuntu.com trusty-backports/universe Sources             
Hit http://ca.archive.ubuntu.com trusty-backports/multiverse Sources           
Hit http://ca.archive.ubuntu.com trusty-backports/main amd64 Packages          
Hit http://ca.archive.ubuntu.com trusty-backports/restricted amd64 Packages    
Hit http://ca.archive.ubuntu.com trusty-backports/universe amd64 Packages      
Hit http://ca.archive.ubuntu.com trusty-backports/multiverse amd64 Packages    
Hit http://ca.archive.ubuntu.com trusty-backports/main i386 Packages           
Hit http://ca.archive.ubuntu.com trusty-backports/restricted i386 Packages     
Hit http://ca.archive.ubuntu.com trusty-backports/universe i386 Packages       
Hit http://ca.archive.ubuntu.com trusty-backports/multiverse i386 Packages     
Hit http://ca.archive.ubuntu.com trusty-backports/main Translation-en          
Hit http://ca.archive.ubuntu.com trusty-backports/multiverse Translation-en    
Hit http://ca.archive.ubuntu.com trusty-backports/restricted Translation-en    
Hit http://ca.archive.ubuntu.com trusty-backports/universe Translation-en      
Hit http://ca.archive.ubuntu.com trusty Release                                
Hit http://ca.archive.ubuntu.com trusty/main Sources                           
Hit http://ca.archive.ubuntu.com trusty/restricted Sources                     
Hit http://ca.archive.ubuntu.com trusty/universe Sources                       
Hit http://ca.archive.ubuntu.com trusty/multiverse Sources                     
Hit http://ca.archive.ubuntu.com trusty/main amd64 Packages                    
Hit http://ca.archive.ubuntu.com trusty/restricted amd64 Packages              
Hit http://ca.archive.ubuntu.com trusty/universe amd64 Packages                
Hit http://ca.archive.ubuntu.com trusty/multiverse amd64 Packages              
Hit http://ca.archive.ubuntu.com trusty/main i386 Packages                     
Hit http://ca.archive.ubuntu.com trusty/restricted i386 Packages               
Hit http://ca.archive.ubuntu.com trusty/universe i386 Packages                 
Hit http://ca.archive.ubuntu.com trusty/multiverse i386 Packages               
Hit http://ca.archive.ubuntu.com trusty/main Translation-en_CA                 
Hit http://ca.archive.ubuntu.com trusty/main Translation-en                    
Hit http://ca.archive.ubuntu.com trusty/multiverse Translation-en              
Hit http://ca.archive.ubuntu.com trusty/restricted Translation-en              
Hit http://ca.archive.ubuntu.com trusty/universe Translation-en_CA             
Hit http://ca.archive.ubuntu.com trusty/universe Translation-en                
Ign http://ca.archive.ubuntu.com trusty/multiverse Translation-en_CA           
Ign http://ca.archive.ubuntu.com trusty/restricted Translation-en_CA           
Fetched 5,569 kB in 11s (479 kB/s)                                             
Reading package lists... Done
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo apt-get install erlang-nox
Reading package lists... Done
Building dependency tree       
Reading state information... Done
You might want to run 'apt-get -f install' to correct these:
The following packages have unmet dependencies:
 erlang-nox : Depends: erlang-base but it is not going to be installed or
                       erlang-base-hipe but it is not going to be installed
              Depends: erlang-asn1 but it is not going to be installed
              Depends: erlang-corba but it is not going to be installed
              Depends: erlang-crypto but it is not going to be installed
              Depends: erlang-diameter but it is not going to be installed
              Depends: erlang-edoc but it is not going to be installed
              Depends: erlang-eldap but it is not going to be installed
              Depends: erlang-erl-docgen but it is not going to be installed
              Depends: erlang-eunit but it is not going to be installed
              Depends: erlang-ic but it is not going to be installed
              Depends: erlang-inets but it is not going to be installed
              Depends: erlang-mnesia but it is not going to be installed
              Depends: erlang-odbc but it is not going to be installed
              Depends: erlang-os-mon but it is not going to be installed
              Depends: erlang-parsetools but it is not going to be installed
              Depends: erlang-percept but it is not going to be installed
              Depends: erlang-public-key but it is not going to be installed
              Depends: erlang-runtime-tools but it is not going to be installed
              Depends: erlang-snmp but it is not going to be installed
              Depends: erlang-ssh but it is not going to be installed
              Depends: erlang-ssl but it is not going to be installed
              Depends: erlang-syntax-tools but it is not going to be installed
              Depends: erlang-tools but it is not going to be installed
              Depends: erlang-webtool but it is not going to be installed
              Depends: erlang-xmerl but it is not going to be installed
 rabbitmq-server : Depends: socat but it is not going to be installed
E: Unmet dependencies. Try 'apt-get -f install' with no packages (or specify a solution).
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo apt-get -f install erlang-nox
Reading package lists... Done
Building dependency tree       
Reading state information... Done
You might want to run 'apt-get -f install' to correct these:
The following packages have unmet dependencies:
 erlang-nox : Depends: erlang-base but it is not going to be installed or
                       erlang-base-hipe but it is not going to be installed
              Depends: erlang-asn1 but it is not going to be installed
              Depends: erlang-corba but it is not going to be installed
              Depends: erlang-crypto but it is not going to be installed
              Depends: erlang-diameter but it is not going to be installed
              Depends: erlang-edoc but it is not going to be installed
              Depends: erlang-eldap but it is not going to be installed
              Depends: erlang-erl-docgen but it is not going to be installed
              Depends: erlang-eunit but it is not going to be installed
              Depends: erlang-ic but it is not going to be installed
              Depends: erlang-inets but it is not going to be installed
              Depends: erlang-mnesia but it is not going to be installed
              Depends: erlang-odbc but it is not going to be installed
              Depends: erlang-os-mon but it is not going to be installed
              Depends: erlang-parsetools but it is not going to be installed
              Depends: erlang-percept but it is not going to be installed
              Depends: erlang-public-key but it is not going to be installed
              Depends: erlang-runtime-tools but it is not going to be installed
              Depends: erlang-snmp but it is not going to be installed
              Depends: erlang-ssh but it is not going to be installed
              Depends: erlang-ssl but it is not going to be installed
              Depends: erlang-syntax-tools but it is not going to be installed
              Depends: erlang-tools but it is not going to be installed
              Depends: erlang-webtool but it is not going to be installed
              Depends: erlang-xmerl but it is not going to be installed
 rabbitmq-server : Depends: socat but it is not going to be installed
E: Unmet dependencies. Try 'apt-get -f install' with no packages (or specify a solution).
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo apt-get -f install
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Correcting dependencies... Done
The following packages were automatically installed and are no longer required:
  libllvm3.5 libntdb1 python-ntdb
Use 'apt-get autoremove' to remove them.
The following extra packages will be installed:
  erlang-asn1 erlang-base erlang-corba erlang-crypto erlang-diameter
  erlang-edoc erlang-eldap erlang-erl-docgen erlang-eunit erlang-ic
  erlang-inets erlang-mnesia erlang-nox erlang-odbc erlang-os-mon
  erlang-parsetools erlang-percept erlang-public-key erlang-runtime-tools
  erlang-snmp erlang-ssh erlang-ssl erlang-syntax-tools erlang-tools
  erlang-webtool erlang-xmerl libodbc1 socat
Suggested packages:
  erlang erlang-manpages erlang-doc fop erlang-ic-java erlang-observer
  libmyodbc odbc-postgresql tdsodbc unixodbc-bin
The following NEW packages will be installed:
  erlang-asn1 erlang-base erlang-corba erlang-crypto erlang-diameter
  erlang-edoc erlang-eldap erlang-erl-docgen erlang-eunit erlang-ic
  erlang-inets erlang-mnesia erlang-nox erlang-odbc erlang-os-mon
  erlang-parsetools erlang-percept erlang-public-key erlang-runtime-tools
  erlang-snmp erlang-ssh erlang-ssl erlang-syntax-tools erlang-tools
  erlang-webtool erlang-xmerl libodbc1 socat
0 upgraded, 28 newly installed, 0 to remove and 129 not upgraded.
1 not fully installed or removed.
Need to get 18.9 MB of archives.
After this operation, 35.9 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-base amd64 1:16.b.3-dfsg-1ubuntu2.1 [6,536 kB]
Get:2 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-asn1 amd64 1:16.b.3-dfsg-1ubuntu2.1 [738 kB]
Get:3 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-mnesia amd64 1:16.b.3-dfsg-1ubuntu2.1 [658 kB]
Get:4 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-runtime-tools amd64 1:16.b.3-dfsg-1ubuntu2.1 [157 kB]
Get:5 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-crypto amd64 1:16.b.3-dfsg-1ubuntu2.1 [70.2 kB]
Get:6 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-public-key amd64 1:16.b.3-dfsg-1ubuntu2.1 [498 kB]
Get:7 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-ssl amd64 1:16.b.3-dfsg-1ubuntu2.1 [559 kB]
Get:8 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-inets amd64 1:16.b.3-dfsg-1ubuntu2.1 [753 kB]
Get:9 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-corba amd64 1:16.b.3-dfsg-1ubuntu2.1 [2,235 kB]
Get:10 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-syntax-tools amd64 1:16.b.3-dfsg-1ubuntu2.1 [289 kB]
Get:11 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-diameter amd64 1:16.b.3-dfsg-1ubuntu2.1 [600 kB]
Get:12 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-xmerl amd64 1:16.b.3-dfsg-1ubuntu2.1 [972 kB]
Get:13 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-edoc amd64 1:16.b.3-dfsg-1ubuntu2.1 [298 kB]
Get:14 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-eldap amd64 1:16.b.3-dfsg-1ubuntu2.1 [91.8 kB]
Get:15 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-erl-docgen amd64 1:16.b.3-dfsg-1ubuntu2.1 [134 kB]
Get:16 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-eunit amd64 1:16.b.3-dfsg-1ubuntu2.1 [137 kB]
Get:17 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-ic amd64 1:16.b.3-dfsg-1ubuntu2.1 [818 kB]
Get:18 http://ca.archive.ubuntu.com/ubuntu/ trusty/main libodbc1 amd64 2.2.14p2-5ubuntu5 [175 kB]
Get:19 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-odbc amd64 1:16.b.3-dfsg-1ubuntu2.1 [50.1 kB]
Get:20 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-snmp amd64 1:16.b.3-dfsg-1ubuntu2.1 [1,497 kB]
Get:21 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-os-mon amd64 1:16.b.3-dfsg-1ubuntu2.1 [94.9 kB]
Get:22 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-parsetools amd64 1:16.b.3-dfsg-1ubuntu2.1 [156 kB]
Get:23 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-percept amd64 1:16.b.3-dfsg-1ubuntu2.1 [136 kB]
Get:24 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-ssh amd64 1:16.b.3-dfsg-1ubuntu2.1 [361 kB]
Get:25 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-webtool amd64 1:16.b.3-dfsg-1ubuntu2.1 [39.5 kB]
Get:26 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-tools amd64 1:16.b.3-dfsg-1ubuntu2.1 [501 kB]
Get:27 http://ca.archive.ubuntu.com/ubuntu/ trusty-updates/main erlang-nox all 1:16.b.3-dfsg-1ubuntu2.1 [17.7 kB]
Get:28 http://ca.archive.ubuntu.com/ubuntu/ trusty/universe socat amd64 1.7.2.3-1 [302 kB]
Fetched 18.9 MB in 14s (1,311 kB/s)                                            
Selecting previously unselected package erlang-base.
(Reading database ... 750716 files and directories currently installed.)
Preparing to unpack .../erlang-base_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-base (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-asn1.
Preparing to unpack .../erlang-asn1_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-asn1 (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-mnesia.
Preparing to unpack .../erlang-mnesia_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-mnesia (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-runtime-tools.
Preparing to unpack .../erlang-runtime-tools_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-runtime-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-crypto.
Preparing to unpack .../erlang-crypto_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-crypto (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-public-key.
Preparing to unpack .../erlang-public-key_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-public-key (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-ssl.
Preparing to unpack .../erlang-ssl_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-ssl (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-inets.
Preparing to unpack .../erlang-inets_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-inets (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-corba.
Preparing to unpack .../erlang-corba_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-corba (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-syntax-tools.
Preparing to unpack .../erlang-syntax-tools_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-syntax-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-diameter.
Preparing to unpack .../erlang-diameter_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-diameter (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-xmerl.
Preparing to unpack .../erlang-xmerl_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-xmerl (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-edoc.
Preparing to unpack .../erlang-edoc_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-edoc (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-eldap.
Preparing to unpack .../erlang-eldap_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-eldap (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-erl-docgen.
Preparing to unpack .../erlang-erl-docgen_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-erl-docgen (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-eunit.
Preparing to unpack .../erlang-eunit_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-eunit (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-ic.
Preparing to unpack .../erlang-ic_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-ic (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package libodbc1:amd64.
Preparing to unpack .../libodbc1_2.2.14p2-5ubuntu5_amd64.deb ...
Unpacking libodbc1:amd64 (2.2.14p2-5ubuntu5) ...
Selecting previously unselected package erlang-odbc.
Preparing to unpack .../erlang-odbc_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-odbc (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-snmp.
Preparing to unpack .../erlang-snmp_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-snmp (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-os-mon.
Preparing to unpack .../erlang-os-mon_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-os-mon (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-parsetools.
Preparing to unpack .../erlang-parsetools_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-parsetools (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-percept.
Preparing to unpack .../erlang-percept_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-percept (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-ssh.
Preparing to unpack .../erlang-ssh_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-ssh (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-webtool.
Preparing to unpack .../erlang-webtool_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-webtool (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-tools.
Preparing to unpack .../erlang-tools_1%3a16.b.3-dfsg-1ubuntu2.1_amd64.deb ...
Unpacking erlang-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package erlang-nox.
Preparing to unpack .../erlang-nox_1%3a16.b.3-dfsg-1ubuntu2.1_all.deb ...
Unpacking erlang-nox (1:16.b.3-dfsg-1ubuntu2.1) ...
Selecting previously unselected package socat.
Preparing to unpack .../socat_1.7.2.3-1_amd64.deb ...
Unpacking socat (1.7.2.3-1) ...
Processing triggers for man-db (2.6.7.1-1ubuntu1) ...
Processing triggers for doc-base (0.10.5) ...
Processing 1 added doc-base file...
Setting up erlang-base (1:16.b.3-dfsg-1ubuntu2.1) ...
Searching for services which depend on erlang and should be started...none found.
Setting up erlang-asn1 (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-mnesia (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-runtime-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-crypto (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-public-key (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-ssl (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-inets (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-corba (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-syntax-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-diameter (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-xmerl (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-edoc (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-eldap (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-erl-docgen (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-eunit (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-ic (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up libodbc1:amd64 (2.2.14p2-5ubuntu5) ...
Setting up erlang-odbc (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-snmp (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-os-mon (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-parsetools (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-percept (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-ssh (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-webtool (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-tools (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up erlang-nox (1:16.b.3-dfsg-1ubuntu2.1) ...
Setting up socat (1.7.2.3-1) ...
Setting up rabbitmq-server (3.6.6-1) ...
Adding group `rabbitmq' (GID 135) ...
Done.
Adding system user `rabbitmq' (UID 127) ...
Adding new user `rabbitmq' (UID 127) with group `rabbitmq' ...
Not creating home directory `/var/lib/rabbitmq'.
 * Starting message broker rabbitmq-server                                                                                                                                                                  [ OK ] 
Processing triggers for libc-bin (2.19-0ubuntu6.9) ...
Processing triggers for ureadahead (0.100.0-16) ...
droid@droidserver:~/software/RabbitMQ/RabbitMQ-3.6.6-1$ sudo dpkg -i rabbitmq-server_3.6.6-1_all.deb 
(Reading database ... 752556 files and directories currently installed.)
Preparing to unpack rabbitmq-server_3.6.6-1_all.deb ...
 * Stopping message broker rabbitmq-server                                                                                                                                                                  [ OK ] 
Unpacking rabbitmq-server (3.6.6-1) over (3.6.6-1) ...
Setting up rabbitmq-server (3.6.6-1) ...
 * Starting message broker rabbitmq-server                                                                                                                                                                  [ OK ] 
Processing triggers for man-db (2.6.7.1-1ubuntu1) ...
Processing triggers for ureadahead (0.100.0-16) ...
```

```sh
droid@droidserver:~$ ps aux | grep rabbitmq
droid    30135  0.0  0.0  15948  2232 pts/10   S+   13:27   0:00 grep --color=auto rabbitmq
```

```sh
droid@droidserver:~$ sudo rabbitmq-server

              RabbitMQ 3.6.6. Copyright (C) 2007-2016 Pivotal Software, Inc.
  ##  ##      Licensed under the MPL.  See http://www.rabbitmq.com/
  ##  ##
  ##########  Logs: /var/log/rabbitmq/rabbit@droidserver.log
  ######  ##        /var/log/rabbitmq/rabbit@droidserver-sasl.log
  ##########
              Starting broker...
 completed with 0 plugins.

```

```sh
droid@droidserver:~$ ps aux | grep rabbit
root     30137  0.0  0.0  75368  4008 pts/10   S+   13:27   0:00 sudo rabbitmq-server
root     30138  0.0  0.0   4448  1692 pts/10   S+   13:27   0:00 /bin/sh /usr/sbin/rabbitmq-server
root     30145  0.0  0.0  74944  3788 pts/10   S+   13:27   0:00 su rabbitmq -s /bin/sh -c /usr/lib/rabbitmq/bin/rabbitmq-server 
rabbitmq 30153  0.0  0.0   4448   808 ?        Ss   13:27   0:00 sh -c /usr/lib/rabbitmq/bin/rabbitmq-server 
rabbitmq 30154  0.0  0.0   4448  1680 ?        S    13:27   0:00 /bin/sh -e /usr/lib/rabbitmq/bin/rabbitmq-server
rabbitmq 30236  0.0  0.0   7500    96 ?        S    13:27   0:00 /usr/local/lib/erlang/erts-8.1/bin/epmd -daemon
rabbitmq 30259  2.6  0.6 3764720 50884 ?       Sl   13:27   0:02 /usr/local/lib/erlang/erts-8.1/bin/beam.smp -W w -A 64 -P 1048576 -t 5000000 -stbt db -zdbbl 32000 -K true -B i -- -root /usr/local/lib/erlang -progname erl -- -home /var/lib/rabbitmq -- -pa /usr/lib/rabbitmq/lib/rabbitmq_server-3.6.6/ebin -noshell -noinput -s rabbit boot -sname rabbit@droidserver -boot start_sasl -kernel inet_default_connect_options [{nodelay,true}] -sasl errlog_type error -sasl sasl_error_logger false -rabbit error_logger {file,"/var/log/rabbitmq/rabbit@droidserver.log"} -rabbit sasl_error_logger {file,"/var/log/rabbitmq/rabbit@droidserver-sasl.log"} -rabbit enabled_plugins_file "/etc/rabbitmq/enabled_plugins" -rabbit plugins_dir "/usr/lib/rabbitmq/lib/rabbitmq_server-3.6.6/plugins" -rabbit plugins_expand_dir "/var/lib/rabbitmq/mnesia/rabbit@droidserver-plugins-expand" -os_mon start_cpu_sup false -os_mon start_disksup false -os_mon start_memsup false -mnesia dir "/var/lib/rabbitmq/mnesia/rabbit@droidserver" -kernel inet_dist_listen_min 25672 -kernel inet_dist_listen_max 25672
rabbitmq 30357  0.0  0.0   4340  1500 ?        Ss   13:27   0:00 erl_child_setup 1024
rabbitmq 30370  0.0  0.0   7464   940 ?        Ss   13:27   0:00 inet_gethost 4
rabbitmq 30371  0.0  0.0   9556  1596 ?        S    13:27   0:00 inet_gethost 4
droid    30464  0.0  0.0  15948  2212 pts/11   S+   13:28   0:00 grep --color=auto rabbit
```


```sh
droid@droidserver:~$ sudo rabbitmqctl status
[sudo] password for droid: 
Status of node rabbit@droidserver ...
[{pid,30259},
 {running_applications,[{rabbit,"RabbitMQ","3.6.6"},
                        {mnesia,"MNESIA  CXC 138 12","4.14.1"},
                        {os_mon,"CPO  CXC 138 46","2.4.1"},
                        {ranch,"Socket acceptor pool for TCP protocols.",
                               "1.2.1"},
                        {rabbit_common,[],"3.6.6"},
                        {xmerl,"XML parser","1.3.12"},
                        {sasl,"SASL  CXC 138 11","3.0.1"},
                        {stdlib,"ERTS  CXC 138 10","3.1"},
                        {kernel,"ERTS  CXC 138 10","5.1"}]},
 {os,{unix,linux}},
 {erlang_version,"Erlang/OTP 19 [erts-8.1] [source] [64-bit] [smp:4:4] [async-threads:64] [hipe] [kernel-poll:true]\n"},
 {memory,[{total,46642760},
          {connection_readers,0},
          {connection_writers,0},
          {connection_channels,0},
          {connection_other,0},
          {queue_procs,2832},
          {queue_slave_procs,0},
          {plugins,0},
          {other_proc,18662056},
          {mnesia,60120},
          {mgmt_db,0},
          {msg_index,45952},
          {other_ets,986936},
          {binary,19384},
          {code,17738802},
          {atom,752561},
          {other_system,8374117}]},
 {alarms,[]},
 {listeners,[{clustering,25672,"::"},{amqp,5672,"::"}]},
 {vm_memory_high_watermark,0.4},
 {vm_memory_limit,3293700096},
 {disk_free_limit,50000000},
 {disk_free,17867169792},
 {file_descriptors,[{total_limit,924},
                    {total_used,2},
                    {sockets_limit,829},
                    {sockets_used,0}]},
 {processes,[{limit,1048576},{used,140}]},
 {run_queue,0},
 {uptime,204},
 {kernel,{net_ticktime,60}}]
```

```sh
droid@droidserver:~$ sudo rabbitmqctl stop
[sudo] password for droid: 
Stopping and halting node rabbit@droidserver ...
```


```sh
droid@droidserver:~$ sudo rabbitmq-server

              RabbitMQ 3.6.6. Copyright (C) 2007-2016 Pivotal Software, Inc.
  ##  ##      Licensed under the MPL.  See http://www.rabbitmq.com/
  ##  ##
  ##########  Logs: /var/log/rabbitmq/rabbit@droidserver.log
  ######  ##        /var/log/rabbitmq/rabbit@droidserver-sasl.log
  ##########
              Starting broker...
 completed with 0 plugins.
Gracefully halting Erlang VM            <---------
```
