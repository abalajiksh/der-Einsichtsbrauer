- ```
  server {
      listen 443 ssl http2;
      listen [::]:443 ssl http2;
  
      server_name sresudharsana.academy;
  
      ssl_certificate /etc/letsencrypt/live/sresudharsana.academy/fullchain.pem;
      ssl_certificate_key /etc/letsencrypt/live/sresudharsana.academy/privkey.pem;
  
      access_log /home/abalaji/sresudharsana.academy/logs/access.log;
      error_log /home/abalaji/sresudharsana.academy/logs/error.log;
  
      root /var/www/ssa;
      index index.php;
  
      location / {
          try_files $uri $uri/ /index.php?$args;
      }
  
  	client_max_body_size 1000M;
  
      location ~ \.php$ {
          try_files $uri =404;
          fastcgi_split_path_info ^(.+\.php)(/.+)$;
          fastcgi_pass unix:/run/php/php7.4-fpm.sock;
          fastcgi_index index.php;
          include fastcgi_params;
  	fastcgi_param  SCRIPT_FILENAME    $document_root$fastcgi_script_name;
      }
  
      # BEGIN SMUSH-WEBP
  location ~* "wp-content\/(uploads\/)(.*.(?:png|jpe?g))" {
    add_header Vary Accept;
    set $image_path $2;
    if (-f "/var/www/insights/wordpress/wp-content/smush-webp/disable_smush_webp") {
      break;
    }
    if ($http_accept !~* "webp") {
      break;
    }
    try_files /wp-content/smush-webp/$image_path.webp $uri =404;
  }
  # END SMUSH-WEBP
  }
  
  server {
      listen 443 ssl http2;
      listen [::]:443 ssl http2;
  
      server_name www.sresudharsana.academy;
  
      ssl_certificate /etc/letsencrypt/live/sresudharsana.academy/fullchain.pem;
      ssl_certificate_key /etc/letsencrypt/live/sresudharsana.academy/privkey.pem;
  
      return 301 https://sresudharsana.academy$request_uri;
  }
  
  server {
      listen 80;
      listen [::]:80;
  
      server_name sresudharsana.academy www.sresudharsana.academy;
  
      return 301 https://sresudharsana.academy$request_uri;
  }
  ```