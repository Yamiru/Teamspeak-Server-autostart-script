# Teamspeak-Server-autostart-script
Teamspeak init.d script to automatic start ts3 server on boot as diferent user.

<img src="https://img.shields.io/badge/Build%20Status-passed-green.svg" alt="passed"> <img src="https://img.shields.io/badge/TS3%20version-ts3server--3.12.0%20x64-red.svg"> <img src="https://img.shields.io/badge/tested%20OS-Debian%20server%2010.3.0%20x64-blue.svg">

##Requirements
- debian based OS
- sudoers   (```apt-get install sudo```)
- nano editor (```sudo apt-get install nano```)
- create folder (```mkdir /opt/ts3server/```)
- go to (```cd /opt/ts3server/```)
í downloaded latest version of [teamspeak3server](https://www.teamspeak.com/downloads#server)
- download (```wget https://files.teamspeak-services.com/releases/server/3.12.0/teamspeak3-server_linux_amd64-3.12.0.tar.bz2```)
- extract (```tar xvf teamspeak3-server_linux_amd64-3.12.0.tar.bz2```)
- remove archive (```rm teamspeak3-server_linux_amd64-3.12.0.tar.bz2```)
- move to head folder (```mv  -v /opt/ts3server/teamspeak3-server_linux_amd64/* /opt/ts3server/```)
- create accept license (```touch .ts3server_license_accepted```) after read LICENSE file
- create user teamspeak (```sudo adduser --disabled-login teamspeak```)
- change folder permissions (```sudo chown teamspeak:teamspeak -R /opt/ts3server```)
- login teamspeak (```su teamspeak```)
- start ts3server (```sh ts3server_startscript.sh start```)
- (copy topken and serveradmin pass)
- login root and continue to create autostart script...  (```su root```)


##How to build
1. Terminal/Console:

    ``` sh
     cd /etc/init.d
    ```
    ``` sh
     nano ts3server
    ```

2. paste/rewrite code from ts3server file [ts3server](https://github.com/Yamiru/Teamspeak-Server-autostart-script/blob/master/ts3server) 
3. CTRL+X
4. Y
(name:ts3server)
5. ENTER 
6. Terminal/Console:


    ```
     sudo chmod 755 /etc/init.d/ts3server
    ```
7. Terminal/Console:

    ```
     sudo update-rc.d ts3server defaults
    ```


8. Terminal/Console:

``` systemctl reboot ```


 
##Commands

stop  TeamSpeak 3 Server :  ```     systectl stop ts3server    ```
    
start TeamSpeak 3 Server :  ```     systectl start ts3server    ```




If you change /etc/init.d/ts3server file --->  ```     systemctl daemon-reload    ```   &  ```  sudo update-rc.d ts3server defaults ```
