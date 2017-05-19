# SSL-Self-Signed-Certificate
Self Signed Certificate used to SSL

    yizli:SSL$ openssl genrsa -out server_privatekey.pem 1024
    Generating RSA private key, 1024 bit long modulus
    .............++++++
    ........++++++
    e is 65537 (0x10001)
    yizli:SSL$ openssl req -new -key server_privatekey.pem -out server_certificate_csr.pem
    You are about to be asked to enter information that will be incorporated
    into your certificate request.
    What you are about to enter is what is called a Distinguished Name or a DN.
    There are quite a few fields but you can leave some blank
    For some fields there will be a default value,
    If you enter '.', the field will be left blank.
    -----
    Country Name (2 letter code) [AU]:FR
    State or Province Name (full name) [Some-State]:
    Locality Name (eg, city) []:PARIS
    Organization Name (eg, company) [Internet Widgits Pty Ltd]:myCompany
    Organizational Unit Name (eg, section) []:DEV
    Common Name (e.g. server FQDN or YOUR name) []:*.myCompany.com
    Email Address []:yizhe.lee.cn@gmail.com
    Please enter the following 'extra' attributes
    to be sent with your certificate request
    A challenge password []:
    An optional company name []:
    yizli:SSL$ openssl x509 -req -days 3650 -in server_certificate_csr.pem -signkey server_privatekey.pem -out server_certificate.pem
    Signature ok
    subject=/C=FR/ST=Some-State/L=PARIS/O=myCompany/OU=DEV/CN=*.myCompany.com/emailAddress=yizhe.lee.cn@gmail.com
    Getting Private key
