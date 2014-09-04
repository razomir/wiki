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

#### Create new certificate request

	openssl req -new -key private_key_file.key -out certificate_request_file.csr

After starting the command, it will askt for the details

#### View details of a certificate request

	openssl req -noout -text -in certificate_request_file.csr

#### Change pem file to key file

	openssl pkey -in private_key.pem -out private_key.key

### Certificate Managment in Puppet

#### List all certificates on Master

	puppet cert list --all

#### Clean a Certificate or Certificate Request

On Master

	puppet cert clean $HOSTNAME

On Client

	rm -rf /var/lib/puppet/ssl/*

Sign a certificate on Master

	puppet cert sign $HOSTNAME
