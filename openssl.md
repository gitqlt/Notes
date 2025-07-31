openssl: Cryptography and SSL/TLS Toolkit
====

## PEM format certificates and private keys (file.pem, file.crt, file.cer, file.key)
### Show content of a PEM certificate:
    $ openssl x509 -in certfile.pem -noout -text
    $ openssl x509 -in certfile.pem -noout -pubkey
- Prints the first one only if more chained
- Options:  
  `-noout`:  do not print the PEM itself (the input)<br>
  `-text`:   print full details<br>
  `-pubkey`: print PEM public key

### Show items of a PEM chain ( file / connection ):
    $ openssl crl2pkcs7 -nocrl -certfile certchain.pem | openssl pkcs7 -print_certs [-noout]
    $ openssl s_client -showcerts -connect <server>:443 </dev/null

### Check a PEM private key (w. pkey/rsa subcommand):
    $ file privkey.pem
    $ openssl pkey -in privkey.pem -noout -check
    $ openssl rsa  -in privkey.pem -noout -check
    $ openssl rsa  -in privkey.pem -noout -text
    $ openssl rsa  -in privkey.pem -pubout

### Check/show a PEM public key:
    $ openssl rsa -in privkey.pem -pubout | openssl rsa -pubin -noout -text
    $ openssl rsa -in pubkey.pem -pubin -noout -text

## PFX (pkcs12) format bundled private key and certificate chain (file.pfx, file.pkcs12)
### Check/show all content of an import-password secured PFX file (may encrypt the private key on-fly)
    $ cat file.pfx | openssl pkcs12 -info [-noenc]
    
### Print the private key only
    $ cat file.pfx | openssl pkcs12 -nocerts [-noenc]
    
### Print the client cert only
    $ cat file.pfx | openssl pkcs12 -clcerts -nokeys
