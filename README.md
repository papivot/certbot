# certbot

# for ROUTE53 

uses - `~/.aws/credentials`

Make sure python3 is the default python

```
sudo apt-get install python3-certbot-dns-route53
```

To generate new certs - 

```
sudo certbot certonly --dns-route53 --dns-route53-propagation-seconds 30 -d "navneetv.com,*.awscloud.navneetv.com,*.gcpcloud.navneetv.com,*.azcloud.navneetv.com,*.pks.awscloud.navneetv.com,*.pks.gcpcloud.navneetv.com,*.pks.azcloud.navneetv.com"
```

or

```
sudo certbot certonly --dns-route53 -d "navneetv.com,*.awscloud.navneetv.com,*.gcpcloud.navneetv.com,*.azcloud.navneetv.com,*.pks.awscloud.navneetv.com,*.pks.gcpcloud.navneetv.com,*.pks.azcloud.navneetv.com"
```

To renew - 
```
sudo certbot renew
```

To delete - 
```
sudo certbot delete
```
---
Certs are stored here - `/etc/letsencrypt/live/domain-name`


`privkey.pem`  : the private key for your certificate.

`fullchain.pem`: the certificate file used in most server software.

`chain.pem`    : used for OCSP stapling in Nginx >=1.3.7.

`cert.pem`     : will break many server configurations, and should not be used without reading further documentation (see link below).


----
- Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/navlab.io/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/navlab.io/privkey.pem
   Your cert will expire on 2020-08-04. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot
   again. To non-interactively renew *all* of your certificates, run
   "certbot renew"
