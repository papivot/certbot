# certbot

# for ROUTE53 

uses - `~/.aws/credentials`

```
sudo pip install certbot_dns_route53==0.31.0
```

or

```
pip3 install certbot_dns_route53==0.31.0`
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


`privkey.pem`  : the private key for your certificate.
`fullchain.pem`: the certificate file used in most server software.
`chain.pem`    : used for OCSP stapling in Nginx >=1.3.7.
`cert.pem`     : will break many server configurations, and should not be used
                 without reading further documentation (see link below).
