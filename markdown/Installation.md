# Installation

***

Bloggy relies on Caddy to function as its webserver. Feel free to reference Caddy's official documentation here: [https://caddyserver.com/docs/install](https://caddyserver.com/docs/install).

This guide also assumes that you already have DNS and port forwarding configured. If you don't know how to do that, check with your domain registrar, cloud provider, or ISP, as the steps can vary.

***

To begin, download Bloggy.

```
git clone https://github.com/mothdotmonster/bloggy bloggy
cd bloggy
```

If you want to simply try out Bloggy, you can use the given Caddyfile to test it out.

`sudo caddy run`

***

If you want to use Bloggy more permanently, a full installation is rather simple. Start by moving the downloaded files to a more permanent location. In this example, we will use `/var/www`.

```
sudo mv * /var/www/
cd /var/www
```

Next, you're going to need to edit the Caddyfile. Using your editor of choice. replace `localhost` with the domain your website will be on (for example, this website uses `bloggy.moth.monster`), and replace `root * ./` with `root * /var/www`. Feel free to make any tweaks you'd like; these are just the minimum to get things working.

Finally, move the Caddyfile into the correct location for it to be used automatically, and restart the Caddy service.

```
mv Caddyfile /etc/caddy/Caddyfile
sudo systemctl reload caddy
```

If everything has been done correctly, your server will begin running with the sample pages.