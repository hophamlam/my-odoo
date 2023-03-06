# This Odoo repo is built from 


sudo docker-compose -f ~/my-odoo/docker-compose.prod.yml up 

sudo docker-compose -f docker-compose.prod.yml up --build --force-recreate -d

sudo git clone https://github.com/hophamlam/my-odoo.git && sudo chmod -R 777 ~/my-odoo/addons && sudo chmod -R 777 ~/my-odoo/etc && sudo mkdir -p ~/my-odoo/postgresql && sudo chmod -R 777 ~/my-odoo/postgresql && sudo nano ~/my-odoo/.env && sudo docker-compose -f ~/my-odoo/docker-compose.prod.yml up 

sudo git -C ~/my-odoo pull

sudo nano ~/my-odoo/.env

sudo rm -rf ~/my-odoo