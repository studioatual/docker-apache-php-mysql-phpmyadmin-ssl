# Docker | Apache 2.4 | PHP 7.3.7 | Mysql 5.7 | Phpmyadmin | SSL

## Installation

#### 1. Create a Self-Signed SSL Certificate

Install Certutil

- <b>sudo apt install libnss3-tools -y</b>

Install mkcert

- <b>wget https://github.com/FiloSottile/mkcert/releases/download/v1.1.2/mkcert-v1.1.2-linux-amd64</b>
- <b>mv mkcert-v1.1.2-linux-amd64 mkcert</b>
- <b>chmod +x mkcert</b>
- <b>sudo cp mkcert /usr/local/bin/</b>

Generate Local CA

- <b>mkcert -install</b>

Generate Local SSL Certificates

- <b>sudo mkcert example.com '\*.example.com' localhost 127.0.0.1 ::1</b>

Copy the certificate <b>example.com+4.pem</b> and key <b>example.com+4-key.pem</b> into folder <b>.docker/apache</b> of your project.

Rename these files to <b>server.pem</b> and <b>server-key.pem</b> and give the permission 644.

- <b>sudo chmod 644 server.pem</b>
- <b>sudo chmod 644 server-key.pem</b>

References

- https://github.com/FiloSottile/mkcert

---

#### 2. Run Docker

Start Server (in background)

- <b>docker-compose up -d</b>

Stop Server

- <b>docker-compose down</b>

Rebuild Server

- <b>docker-compose up -d --build</b>

---
