```bash
server {
    listen 8000;  # Change this to whatever port you want (1024–65535)
    server_name localhost;

    root /home/YOUR_USERNAME/www;  # Replace with your actual home dir path
    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    # Optional: PHP support
    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock; # Adjust PHP version/socket path
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```