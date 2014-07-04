## Certificate Management

#### check if the ssl cert is ok

	openssl rsa -in [path to filename].pem -check

#### check ssl cert details

	openssl x509 -in [path to filename].crt -text -noout

#### get all issuers from crt certificates on machine

for crt format

	for i in $(locate .crt); do openssl x509 -in $i -text -noout |grep Issuer: ; done

for pem format

	for i in $(locate .pem); do openssl rsa -in $i -text -noout ; done
