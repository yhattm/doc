# Create a self-signed certificate
## openssl req -x509 -nodes -days 3650 -newkey rsa:4096 -keyout ca_key.pem -out ca_cert.pem -new -sha512
# get public key
## openssl x509  -in eabab4c8ba-certificate.pem.crt -pubkey
