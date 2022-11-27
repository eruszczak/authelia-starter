# Setup traefik with local TLS
1. `git clone git@github.com:erykio/authelia-starter.git`
2. `cd authelia-starter`
3. Download [mkcert](https://github.com/FiloSottile/mkcert)
4. `mkcert -install`
5. `mkcert -key-file certs/key.pem -cert-file certs/cert.pem localtest.me *.localtest.me`
6. `docker-compose up`
7. now you can visit https://traefik.localtest.me (public access) and https://page1.localtest.me (secured by Authelia)

Authelia Portal:
- login: authelia
- password: authelia
