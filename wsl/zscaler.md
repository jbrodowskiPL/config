# Zscaler

### To add Zscaler certificate to the Debian system do the following:

1. Type `certmgr.msc` using Windows search button
1. In the window, find out the certificate of the proxy:

   ```
   Intermediate Certification Authorities > Certificates > Zscaler Root CA
   ```

1. Double click the certificate row and go to `Details tab`
1. Click button `Copy to File`
1. Select `Base-64 encoded X.509 (.CER)`
1. Choose the path and finish the export. Name the file `myproxy.cer`
1. Copy this certification file into your WSL distro
1. Install openssl package if not installed:

   ```
   apt install -y openssl
   ```

1. Use the following command line to convert

   ```
   openssl x509 -inform PEM -in myproxy.cer -out myproxy.crt
   ```

1. Install additional packages and move file to a final destination:

   ```
   apt install -y ca-certificates
   cp myproxy.crt /usr/local/share/ca-certificates
   update-ca-certificates
   ```

Links:

- [Docker with WSL 2, SSL Proxy and SSL Certificate Problem](https://kontext.tech/article/1065/docker-with-wsl-2-ssl-proxy-and-ssl-certificate-problem)