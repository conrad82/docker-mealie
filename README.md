# docker-mealie
Running mealie from docker-compose - getting started with docker

## Quick-start guide:
1. Set up raspberry pi with raspbian OS or Ubuntu server (64-bit)
  - Ubuntu server is recommended, but raspian OS is more supported if problems occur.
    - Raspbian: https://www.raspberrypi.org/software/
      -  Detailed guide: https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up
    - Ubuntu server: https://ubuntu.com/download/raspberry-pi
    - If headless install (no keyboard/mouse/monitor), see headless raspberry pi guide: https://www.raspberrypi.org/documentation/configuration/wireless/headless.md
2. Connect to Raspberry Pi using keyboard/mouse or ssh
3. Install git and docker-compose, and start docker
  - Open up terminal, or via ssh:
```
sudo apt update
sudo apt install git docker-compose
sudo systemctl start docker
```
4. Download this repository
```
git clone https://github.com/conrad82/docker-mealie.git
```
5. Run the service
```
cd docker-mealie
sudo docker-compose up
```
If you want it to run in the background (daemon), use command `sudo docker-compose up -d` instead.

6. Test the service
  - Open up browser
  - Go to http://*raspberry-pi-ip*:9000
     - If you are running locally, you can also use address http://localhost:9000
7. Finished

***
### Info
- To run via ssh, you must find the raspberry pi ip address 
  - usually by logging on to router and looking for connected ip's. 
  - it may be possible to use address `raspberrypi` or `raspberrypi.local` , depending on your router DHCP server.
- The docker container settings are shown in `docker-compose.yml`. 
  - More details about docker-compose can be found here: https://docs.docker.com/compose/
- Headless Ubuntu wifi on first install
  - In system-boot partition:
    - create empty file `ssh` on install disk
    - edit the `network-config` file to add your Wi-Fi credentials. An example is already included in the file, you can simply adapt it.
