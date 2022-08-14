# Before begin
This repo takes advantage of https://github.com/minhng92/odoo-13-docker-compose. I'm re-use it with a bit custom for my purpose.
# Installing Odoo 13 with one command.

## Quick start
(Supports multiple Odoo instances on one server)Install [docker](https://docs.docker.com/get-docker/) and [docker-compose](https://docs.docker.com/compose/install/) yourself, then run:
```bash
curl -s https://raw.githubusercontent.com/minhng92/odoo-13-docker-compose/master/run.sh | sudo bash -s odoo-o
```

to set up first Odoo instance @ `localhost:10013` (default master password: `minhng.info`)

Some arguments:

-   First argument (**odoo-one**): Odoo deploy folder
-   Second argument (**10013**): Odoo port
-   Third argument (**20013**): live chat port

If `curl` is not found, install it:
```bash
apt-get install curl
# or
yum install curl
```

**If you get the permission issue**, change the folder permission to make sure that the container is able to access the directory:

```bash
git clone https://github.com/minhng92/odoo-13-docker-compose
sudo chmod -R 777 addons
sudo chmod -R 777 etc
mkdir -p postgresql
sudo chmod -R 777 postgresql
```

### Custom addons

The  **addons/**  folder contains custom addons. Just put your custom addons if you have any.

### Odoo configuration & log

-   To change Odoo configuration, edit file:  **etc/odoo.conf**.
-   Log file:  **etc/odoo-server.log**
-   Default database password (**admin_passwd**) is  `minhng.info`, please change it @  [etc/odoo.conf#L60](https://github.com/minhng92/odoo-13-docker-compose/blob/master/etc/odoo.conf#L60)

### Live chat

We exposed port  **20013**  for live-chat on host (following above setting)

Configuring  **nginx**  to activate live chat feature (in production):

```apacheconf
#...
server {
    #...
    location /longpolling/ {
        proxy_pass http://0.0.0.0:20013/longpolling/;
    }
    #...
}
#...
```

-   odoo:13.0
-   postgres:11