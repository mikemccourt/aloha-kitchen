# Aloha Kitchen Home Page

This is a McCourt Digital project, working with Shawn Thomas, to make a homepage for Aloha Kitchen.

We are going to host this somewhere, eventually -- still need to figure that out.

### WSL instructions
I installed stuff according to [these instructions](https://chabolla.dev/wamp-lamp-stack-install-on-windows/), which were very helpful.  Once everything is active,
you should be able to confirm by checking

* http://localhost/
* http://localhost/phptest.php
* http://localhost/phpmyadmin/

To get the webserver to point to our website, I added a link:
```
sudo ln -s /mnt/c/Users/track/Documents/projects/aloha-kitchen /var/www/html/aloha
```
This should be enough if the `/etc/apache2/apache2.conf` file has something like this
```
<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
</Directory>
```

#### PHPAdmin stuff
I had to initially go to localhost:80/phpmyadmin/ the first time, but after that it didn't seem necessary.

I also had to edit /etc/phpmyadmin/config-db.php from 
$dbserver='localhost';
to
$dbserver='127.0.0.1';
