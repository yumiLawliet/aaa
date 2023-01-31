# aaa
C:\Program*Files\OpenSSL-Win64\bin
.\openssl.exe genrsa -out root.key
.\openssl req -x509 -new -nodes -key root.key -sha256 -days 365 -out root.crt -config openssl-1.cnf -subj "/C=RU/ST=Moskow/L=Moslow/O=demo lab/OU=IT/CN=demo.lab/emailAddress=admin@demo.lab"
