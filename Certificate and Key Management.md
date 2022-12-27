# Certificate and Key Management
Teleport: [keys.thismuch.net](https://keys.thismuch.net)

## Tool Host
`keys.thismuch.net` hosts tools for managing SSL and SSH keys and certificates

## SSL
A wildcard certificate for  `*.thismuch.net` is maintained using [Let's Encrypt](https://letsencrypt.org/ ) and [acme.sh](https://github.com/acmesh-official/acme.sh) running on `keys.thismuch.net`.

For testing purposes, set the CA server to 
```
acme.sh --set-default-ca --server letsencrypt_test
```
acme.sh  --register-account  --server letsencrypt  -m  troy@thismuch.net
```

```
And for real certificates:
```
acme.sh --set-default-ca --server letsencrypt
```
acme.sh  --register-account  --server letsencrypt  -m  troy@thismuch.net
```
```


```
acme.sh --issue -d '*.thismuch.net' --dns --yes-I-know-dns-manual-mode-enough-go-ahead-please
```
Go to [no-ip]() and add the `TXT` record to `_acme-challenge.thismuch.net`
```
acme.sh --renew -d '*.thismuch.net'   --yes-I-know-dns-manual-mode-enough-go-ahead-please
```

#### Renewals
| Date  |  Notes|
|------- | -------|
| 8 Aug 2022 | Initial registration |


## Teleport
Install [Teleport](https://goteleport.com/)

[Teleport Clients/Downloads](curl -O teleport-v10.1.2-windows-amd64-bin.zip https://get.gravitational.com/teleport-v10.1.2-windows-amd64-bin.zip)

```
acme.sh --install-cert -d '*.thismuch.net' --key-file /var/lib/teleport/privkey.pem --fullchain-file /var/lib/teleport/fullchain.pem

sudo teleport configure -o file     --cluster-name=keys.thismuch.net     --public-addr=keys.thismuch.net:443     --cert-file=/var/lib/teleport/fullchain.pem     --key-file=/var/lib/teleport/privkey.pem

systemctl enable teleport
```