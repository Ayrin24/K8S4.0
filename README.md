Задание 1. 

<img width="848" height="440" alt="image" src="https://github.com/user-attachments/assets/3d83bb8d-eb08-4ff5-8447-5fa44bff4174" />

<img width="593" height="238" alt="image" src="https://github.com/user-attachments/assets/c0c5cb2e-af76-4717-97f5-1dd2d5bed323" />

Задание 2.

<img width="569" height="207" alt="image" src="https://github.com/user-attachments/assets/a53bed77-2b29-4366-bc0b-d45fc7593968" />

<img width="745" height="52" alt="image" src="https://github.com/user-attachments/assets/1682076a-0f80-4d02-88a8-eaae34033d8b" />

````
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout tls.key -out tls.crt \
  -subj "/CN=62-84-118-36.sslip.io" \
  -addext "subjectAltName=DNS:62-84-118-36.sslip.io"
````

Задание 3.

<img width="892" height="397" alt="image" src="https://github.com/user-attachments/assets/8d9ecddb-c0cd-46b4-b7d5-a793e7e96643" />

<img width="1288" height="456" alt="image" src="https://github.com/user-attachments/assets/42c1a8fe-14d2-4889-9cbc-47279a87c035" />

````
openssl genrsa -out developer.key 2048
openssl req -new -key developer.key -out developer.csr -subj "/CN=developer"
openssl x509 -req -in developer.csr \
  -CA /var/snap/microk8s/current/certs/ca.crt \
  -CAkey /var/snap/microk8s/current/certs/ca.key \
  -CAcreateserial -out developer.crt -days 365
````
