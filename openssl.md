Show content of a PEM certificate (the first one if more chained) (Privacy Enhanced Mail)
====
    $ openssl x509 -in certfile.pem -noout -text
    $ openssl x509 -in certfile.pem -noout -pubkey

Options:

`-noout`:  do not print the PEM itself (the input)
 
Check a PEM public key:
=====
    $ openssl rsa -in pubkey.pem -pubin -noout -text

Check a PEM private key:
=====
    $ openssl rsa -in privkey.pem -noout -check
