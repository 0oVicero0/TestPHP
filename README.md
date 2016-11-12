# TestPHP
```
apt-get install -y php5-common php5-cli php5-cgi php5-fpm php5-curl php-apc
```
```
apt-get install -y p7zip-full
wget https://github.com/0oVicero0/rpvideo/archive/master.zip
7z x master.zip -o/usr/share/nginx/www/player
```
```
	server {
		listen 80;		
		server_name 1024.vicer.xyz;
		root /usr/share/nginx/www/player;
		location / {
		        index index.html index.php;
		}
		location ~ \.php$ {
		        fastcgi_split_path_info ^(.+\.php)(/.+)$;
			fastcgi_pass unix:/var/run/php5-fpm.sock;
			fastcgi_index index.php;
			#fastcgi_param SCRIPT_FILENAME html$fastcgi_script_name;
			include fastcgi_params;
		}
	}
```
```
chown -R www-data:www-data /usr/share/nginx/www/player
chmod -R 755 /usr/share/nginx/www
```
