## Usage

# Create Self-Signed Root CA Certificate
openssl req -new -newkey rsa:2048 -sha256 -days 365 -nodes -x509 -extensions v3_ca -keyout conf/ssl_cert/myCA.pem -out conf/ssl_cert/myCA.pem

# Create a DER-encoded certificate to import into users' browsers
openssl x509 -in conf/ssl_cert/myCA.pem -outform DER -out conf/ssl_cert/myCA.der

Firefox -> Preferences -> Privacy & Security -> View Certificates -> Import

# Create username and password for access to proxy (replace username123/password123)
htpasswd -b conf/squid.passwd username123 password123

