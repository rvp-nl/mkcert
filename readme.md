# Example scrips to create a root certificate and a server certificate

## Examples

# Create self-signed root certificate
    export CERT_NAME=myroot-ca
    ./mk-root-cert.sh

# Create signed server certificate
    export CERT_NAME=myserver
    export ROOT_CERT=myroot-ca
    export ALT_DNS=myserver
    export ALT_IP=192.168.56.101
    ./mk-server-cert.sh

## Install root certificate (Ubuntu)
    sudo apt-get install -y ca-certificates
    sudo cp my-root-ca.crt /usr/local/share/ca-certificates
    sudo update-ca-certificates
