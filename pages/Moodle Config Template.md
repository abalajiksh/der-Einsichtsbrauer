- ```
  server {
      listen 443 ssl http2;
      listen [::]:443 ssl http2;
      root /var/www/courses.theskillcraft.com;
      index  index.php index.html index.htm;
      server_name courses.theskillcraft.com;
  
      ssl_certificate /home/cert/fullchain.pem;
      ssl_certificate_key /home/cert/privkey.pem;
  
      ssl_protocols TLSv1 TLSv1.1 TLSv1.2 TLSv1.3;
      ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
  
      access_log /home/logs/access.log;
      error_log /home/logs/error.log;
      
      autoindex off;
      add_header Strict-Transport-Security "max-age=31536000;  includeSubDomains";
      add_header X-Frame-Options SAMEORIGIN;
      add_header X-Content-Type-Options nosniff;
      client_max_body_size 1000M;
  
      location / {
      try_files $uri $uri/ =404;        
      }
   
      location /dataroot/ {
      internal;
      alias /var/www/moodledata/;
      }
  
      location ~ [^/]\.php(/|$) {
          include snippets/fastcgi-php.conf;
          fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
          fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
          include fastcgi_params;
      }
  }
  
  server {
      listen 443 ssl http2;
      listen [::]:443 ssl http2;
  
      server_name www.courses.theskillcraft.com;
  
      ssl_certificate /home/cert/fullchain.pem;
      ssl_certificate_key /home/cert/privkey.pem;
  
      return 301 https://courses.theskillcraft.com$request_uri;
  }
  
  server {
      listen 80;
      listen [::]:80;
  
      server_name courses.theskillcraft.com www.courses.theskillcraft.com;
  
      return 301 https://courses.theskillcraft.com$request_uri;
  }
  ```