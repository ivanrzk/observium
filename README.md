# Docker container for Observium Community Edition
Observium is network monitoring with intuition. It is a low-maintenance auto-discovering network monitoring platform supporting a wide range of device types, platforms and operating systems including Cisco, Windows, Linux, HP, Juniper, Dell, FreeBSD, Brocade, Netscaler, NetApp and many more. Observium focuses on providing a beautiful and powerful yet simple and intuitive interface to the health and status of your network. For more information, go to http://www.observium.org site.

## Usage
### Use Docker Composer
- Follow instuctions below to create extra working directory of docker containers (You can change /home/docker directory to your desired directory).
```
  $ cd /home/docker
  $ git clone https://github.com/ivanrzk/observium.git observium
  $ cd observium
```
- Change some environments in .env to your appropreate values in docker-compose.yml file, e.g. OBSERVIUM_ADMIN_USER, OBSERVIUM_ADMIN_PASS.

- Build image.
```
  $ docker-compose build
```

- Run both database and observium containers.
```
  $ docker-compose up
```

- For your first time, you may add a new device, discover and poll that device. It is given an idea below (I follow https://docs.observium.org/install_debian/#perform-initial-discovery-and-poll).
```
  $ docker-compose exec app /opt/observium/add_device.php <hostname> <community> v2c
  $ docker-compose exec app /opt/observium/discovery.php -h all
  $ docker-compose exec app /opt/observium/poller.php -h all
```
## Source Repository
Based on source of project https://github.com/somsakc/docker-observium
## Credits
- Official Observium web site [https://www.observium.org]
- Ubuntu installation from Observium web site [https://docs.observium.org/install_debian/]
