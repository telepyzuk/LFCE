
# Question

The website you currently manage has been extended to include an SSL secure application extension. You have been assigned the task of installing a webserver on this system and configuring the SSL properties according to your organization's security policy. Complete the following steps to ensure the web server is correctly configured:

Install a webserver and set it to listen on port `799` for `HTTP` traffic and `8993` for `HTTPS` traffic.
Using the `prod_pk.key` Private Key file in `/opt/CESC00101/ssl` , generate a Certificate Signing Request named `/opt/CESC00101/ssl/srv.csr` with the following values:

    Country code: TT
    State or Province: Lost West
    City: Gotham City
    Organization name: Earthco
    OU Name: MGMT
    Server Name: app.example.com
    Email address: nemo@example.com

Generate a self-signed certificate named ca.crt in `/opt/CESC00101/ssl` , using the `CSR` you just generated and the `prod_pk.key` private key file, both of which are located in `/opt/CESC00101/ssl` . The certificate should expire in `730` days.
Copy the files to the following locations:

    Certificate: /etc/pki/tls/certs/
    Key: /etc/pki/tls/private/
    Certificate Signing Request: /etc/pki/tls/private/

Update the webserver configuration file to include the location of the Certificate file and the Certificate Key.

The webserver should be started, and configured to automatically start on boot

# Question Weight

3%

# did it??

Couldn't do it...

