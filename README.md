# Setup traefik with local TLS

1. `git clone git@github.com:erykio/authelia-starter.git`
2. `cd authelia-starter`
3. Download [mkcert](https://github.com/FiloSottile/mkcert)
4. `mkcert -install`
5. `mkcert -key-file certs/key.pem -cert-file certs/cert.pem example.com *.example.com`
6. append to `/etc/hosts`
```
127.0.0.1 traefik.example.com
127.0.0.1 authelia.example.com
127.0.0.1 page1.example.com
127.0.0.1 page2.example.com
127.0.0.1 page3.example.com
```
7. `docker-compose up`
8. now you can visit https://traefik.example.com (public access) and https://page1.example.com (secured by Authelia)

Authelia Portal:
- login: authelia
- password: authelia
