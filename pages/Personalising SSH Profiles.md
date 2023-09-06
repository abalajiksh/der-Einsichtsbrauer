- `nano ~/.ssh/config`
- ```
  Host acme
  	Hostname acme.linuxcloud.com
  # ssh root@acme.linuxcloud.com -> ssh acme
      
  Host potato
  	Hostname 172.27.64.03
  # ssh root@172.27.64.03 -> ssh potato
      
  Host skynet
  	Hostname skynet.linuxcloud.com
      User admin
  # ssh admin@skynet.linuxcloud.com -> ssh skynet
  
  Host shimra
  	Hostname shimra.linuxcloud.com
      User sannia
      Port 2222
  # ssh sannia@shimra.linuxcloud.com -p 2222 -> ssh shimra
  
  Host bitbucket-personal
          HostName bitbucket.org
          User git
          IdentityFile ~/.ssh/id_rsa_personal
          IdentitiesOnly yes
  ```