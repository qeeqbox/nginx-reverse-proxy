# nginx-reverse-proxy
Nginx reverse proxy for testing

#### Run
sudo docker-compose down && sudo docker-compose build --no-cache  && sudo docker-compose up

#### Output (Honeypots)
```sh
honeypots_1     | [x] Parsing honeypot [normal]
honeypots_1     | {"action": "process", "dest_ip": "0.0.0.0", "dest_port": "80", "password": "test", "server": "http_server", "src_ip": "0.0.0.0", "src_port": "80", "status": "success", "timestamp": "2022-02-08T20:41:40.979564", "username": "test"}
honeypots_1     | {"action": "connection", "data": {"Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8", "Accept-Encoding": "gzip, deflate", "Accept-Language": "en-US,en;q=0.5", "Connection": "close", "Host": "0.0.0.0", "Upgrade-Insecure-Requests": "1", "User-Agent": "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:96.0) Gecko/20100101 Firefox/96.0", "X-Forwarded-For": "172.25.0.1", "X-Real-Ip": "172.25.0.1", "method": "GET", "uri": "/"}, "dest_ip": "0.0.0.0", "dest_port": "80", "server": "http_server", "src_ip": "172.25.0.1", "src_port": "59440", "timestamp": "2022-02-08T20:41:45.633407"}
honeypots_1     | {"action": "GET", "dest_ip": "0.0.0.0", "dest_port": "80", "server": "http_server", "src_ip": "172.25.0.1", "src_port": "59440", "timestamp": "2022-02-08T20:41:45.634387"}
reverseproxy_1  | 172.25.0.1 - - [08/Feb/2022:20:41:45 +0000] "GET / HTTP/1.1" 200 1126 "-" "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:96.0) Gecko/20100101 Firefox/96.0"
honeypots_1     | {"action": "connection", "data": {"Accept": "image/avif,image/webp,*/*", "Accept-Encoding": "gzip, deflate", "Accept-Language": "en-US,en;q=0.5", "Connection": "close", "Host": "0.0.0.0", "Referer": "http://0.0.0.0:8080/", "User-Agent": "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:96.0) Gecko/20100101 Firefox/96.0", "X-Forwarded-For": "172.25.0.1", "X-Real-Ip": "172.25.0.1", "method": "GET", "uri": "/favicon.ico"}, "dest_ip": "0.0.0.0", "dest_port": "80", "server": "http_server", "src_ip": "172.25.0.1", "src_port": "59442", "timestamp": "2022-02-08T20:41:45.707984"}
honeypots_1     | {"action": "GET", "dest_ip": "0.0.0.0", "dest_port": "80", "server": "http_server", "src_ip": "172.25.0.1", "src_port": "59442", "timestamp": "2022-02-08T20:41:45.708123"}
reverseproxy_1  | 172.25.0.1 - - [08/Feb/2022:20:41:45 +0000] "GET /favicon.ico HTTP/1.1" 200 1126 "http://0.0.0.0:8080/" "Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:96.0) Gecko/20100101 Firefox/96.0"
```
