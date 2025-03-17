### Show content of a PEM certificate
(only the first one if more chained)

    $ openssl x509 -in certfile.pem -noout -text
    $ openssl x509 -in certfile.pem -noout -pubkey

Options:

`-noout`:  do not print the PEM itself (the input)<br>
`-text`:   print full details<br> `-pubkey`: print PEM public key

### Show items of a PEM chain

    $ openssl crl2pkcs7 -nocrl -certfile certchain.pem | openssl pkcs7 -print_certs [-noout]

### Check a PEM private key (w. pkey/rsa subcommand):
    $ file privkey.pem
    $ openssl pkey -in privkey.pem -noout -check
    $ openssl rsa -in privkey.pem -noout -check
    $ openssl rsa -in privkey.pem -noout -text
    $ openssl rsa -in privkey.pem -pubout

### Check/show a PEM public key:
    $ openssl rsa -in privkey.pem -pubout | openssl rsa -pubin -noout -text
    $ openssl rsa -in pubkey.pem -pubin -noout -text
