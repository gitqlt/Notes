certbot (formerly letsencrypt) Tool to obtain certs from Let's Encrypt and autoenable HTTPS
====

#### Get TXT record for DNS challenge
    (Package certbot)
    $ mkdir -p /tmp/lets/{live,work,logs}
    $ certbot certonly --manual --preferred-challenges dns -d srv1.dev.mycompany.com --config-dir /tmp/lets --work-dir /tmp/lets/work --logs-dir /tmp/lets/logs

    (Package acme.sh)
    $ acme.sh --issue --dns -d srv1.dev.mycompany.com --yes-I-know-dns-manual-mode-enough-go-ahead-please --test
