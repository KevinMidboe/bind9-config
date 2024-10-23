# Bind9 config

My current bind9 configuration for local datacenter.

## Setup

Generating tsig & rndc key for dynamic DNS updates.

```bash
tsig-keygen -a hmac-sha512 >> /etc/bind/keys.conf
tsig-keygen -a hmac-sha512 rndc-key >> /etc/bind/keys.conf
```

## Using as a template

The main files to edit are the `named.conf.local` and `zones/*` files. These are currently referencing `schleppe` as a TLD. First rename or crate a new `zones/db.[YOUR_DOMAIN_HERE]` file, then update `named.conf.local` import to reflect name change. 
