# PortfolioWebsite

This repository contains a stylish, easy-to-customize personal portfolio template created using HTML5, CSS and JavaScript.
It is lightweight,fully responsive and loaded with Font Awesome. 
### Configure Nginx and place in the following directory: /etc/nginx/sites-available

We will configure Nginx so that it will pass web requests to the socket file in the project directory.

First we will create a server block configuration file:
```
sudo nano /etc/nginx/sites-available/shakespeare
```

Copy the below text and paste it. Make sure to change any values specific to your own project, server IP and server/PC directory paths.
```
### Configure Nginx and place in the following directory: /etc/nginx/sites-available

We will configure Nginx so that it will pass web requests to the socket file in the project directory.

First we will create a server block configuration file:
```
sudo nano /etc/nginx/sites-available/shakespeare
```

Copy the below text and paste it. Make sure to change any values specific to your own project, server IP and server/PC directory paths.
```
server {
  listen 80;
  listen [::]:80;

  root /var/www/mohamedabdulaziz.com;

  index index.html;

  server_name mohamedabdulaziz.com www.mohamedabdulaziz.com;

  location / {
    try_files $uri $uri/ =404;
  }
}

```

To enable the Nginx server block configuration we've just created, link the file to the sites-enabled directory:
```
sudo ln -s /etc/nginx/sites-available/mohamedabdulaziz.com /etc/nginx/sites-enabled
```

Test for syntax errors:
```
sudo nginx -t
```

If it returns a successful response then restart the Nginx process as well as the uWSGI service you made earlier:
```
sudo systemctl restart nginx
```

Allow access to the Nginx server through the firewall:
```
sudo ufw allow 'Nginx Full'
```

You can see a demo of the project here:
```
https://mohamedabdulaziz.com
```
```

To enable the Nginx server block configuration we've just created, link the file to the sites-enabled directory:
```
sudo ln -s /etc/nginx/sites-available/shakespeare /etc/nginx/sites-enabled
```

Test for syntax errors:
```
sudo nginx -t
```

If it returns a successful response then restart the Nginx process as well as the uWSGI service you made earlier:
```
sudo systemctl restart nginx
```

Allow access to the Nginx server through the firewall:
```
sudo ufw allow 'Nginx Full'
```

You can see a demo of the project here:
```
https://shakespeare.mohamedabdulaziz.com
```
To view a live demo, [click here](https://www.mohamedabdulaziz.com/).
