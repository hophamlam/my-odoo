sudo docker-compose -f ~/my-odoo/docker-compose.prod.yml up 

sudo docker-compose -f docker-compose.prod.yml up --build --force-recreate -d

test ci-cd

curl -s https://raw.githubusercontent.com/hophamlam/my-odoo/main/run.sh | sudo bash -s my-odoo 10014 20014

sudo git clone https://github.com/hophamlam/my-odoo.git

sudo git pull -c ~/my-odoo

sudo chmod -R 777 ~/my-odoo/addons && sudo chmod -R 777 ~/my-odoo/etc && sudo mkdir -p ~/my-odoo/postgresql && sudo chmod -R 777 ~/my-odoo/postgresql

sudo nano .env