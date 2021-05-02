## Application
	Reverse Proxy + config for self-hosted apps on my personal cluster

# Usage
	Launch with docker-compose up --build -d
# Installation
	Pre-Reqs: 
		- Docker Installed
		- Docker-Compose Installed
		- Set DOMAIN in ./nginx/configs/default.conf
# Adding Services
	Create an appropriate docker-compose to launch new service
	Add to current docker-compose.yaml file
	Create nginx proxy config file of the form: 

		server{
			listen 80;
			server_name <SUBDOMAIN>.<DOMAIN>; 

			location / {
			# proxy_set_header Host $host;
			proxy_pass http://<SUBDOMAIN>:3000;
			# proxy_redirect off;
			}
		}

# TODO
	- SSL Setup
	- Automate service add
	- Services to add: 
	- 	Jenkins
	- 	C951 / Capstone
	- 	Wordpress
	- 	Heimdall	
