
конфиг потом повершел


C:\Program*Files\OpenSSL-Win64\bin

.\openssl.exe genrsa -out root.key

.\openssl req -x509 -new -nodes -key root.key -sha256 -days 365 -out root.crt -config openssl-1.cnf -subj "/C=RU/ST=Moskow/L=Moslow/O=demo lab/OU=IT/CN=demo.lab/emailAddress=admin@demo.lab"

.\openssl.exe genrsa -out iwtm.key

.\openssl.exe req -new -sha256 -config openssl-1.cnf -key iwtm.key -out iwtm.csr

.\openssl x509 -req -in "iwtm.csr" -CA "root.crt" -CAkey "root.key" -CAcreateserial -out "iwtm.crt" -extensions v3_req -extfile "openssl-1.cnf" -subj "/C=RU/ST=Moskow/L=Moskow/O=demolab/OU=IT/CN=iwtm/emailAddress=iwtm@demo.lab"

.\openssl pkcs12 -export -in iwtm.crt -inkey iwtm.key -in root.crt -inkey root.key -out out.p12 -password pass:xxXX1234


192.168.99.15

папка /opt/iw/tm5/etc/certificatiiikvjlkcx

в ивтм /etc/nginx/conf.d/iwtm.conf

редачить ивтм кей и срт

systemctl restart nginx.service

