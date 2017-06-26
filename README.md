# Teamspeak-Server-autostart-script
Teamspeak init.d script to automatic start ts3 server on boot as diferent user.

https://img.shields.io/badge/Build%20Status-passed-green.svg
!(https://img.shields.io/badge/TS3%20version-ts3server--3.0.13.4%20x64-red.svg)
!(https://img.shields.io/badge/tested%20OS-Ubuntu%20server%2016.10%20x64-blue.svg)
##Requirements
- debian based OS
- sudoers   (```aptitude install sudo```)
- nano editor (```sudo apt-get install nano```)
- installed latest version of [teamspeak3server](https://www.teamspeak.com/downloads#server) 
- dir location of ts3server /opt/ts3server/
- permission for teamspeak user (```sudo chown teamspeak:teamspeak -R /opt/ts3server```)
- user teamspeak  (```sudo adduser --disabled-login teamspeak```)

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

``` reboot ```


 
##Commands

stop  TeamSpeak 3 Server :  ```     service ts3server stop    ```
    
start TeamSpeak 3 Server :  ```     service ts3server start    ```




If you change /etc/init.d/ts3server file --->  ```     systemctl daemon-reload    ```   &  ```  sudo update-rc.d ts3server defaults ```
