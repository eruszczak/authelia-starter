# Set up [Authelia](https://www.authelia.com/) integrated with [Traefik](https://traefik.io/traefik/) reverse proxy
1. `git clone git@github.com:erykio/authelia-starter.git`
2. `cd authelia-starter`
3. Download [mkcert](https://github.com/FiloSottile/mkcert)
4. `mkcert -install`
5. `mkcert -key-file certs/key.pem -cert-file certs/cert.pem localtest.me *.localtest.me`
6. `docker-compose up`

# Apps
To access any of the following applications, you will be redirected to the [Authelia portal](https://authelia.localtest.me/) where you will need to log in with the appropriate user.
<table>
    <tr>
        <th>Application</th>
        <th>Access groups</th>
        <th>Login/Password</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>https://traefik.localtest.me</td>
        <td>admin</td>
        <td>-</td>
        <td>Traefik proxy dashboard</td>
    </tr>
    <tr>
        <td>https://ldap.localtest.me</td>
        <td>-</td>
        <td>cn=admin,dc=localtest,dc=me / password</td>
        <td>Web-based LDAP client</td>
    </tr>
    <tr>
        <td>https://page1.localtest.me</td>
        <td>admin, page1</td>
        <td>-</td>
        <td>Example webpage</td>
    </tr>
    <tr>
        <td>https://page2.localtest.me</td>
        <td>admin, page2</td>
        <td>-</td>
        <td>Example webpage</td>
    </tr>
</table>

# Users
You can use username or email for login. You can also reset the default password through a Authelia portal (you will receive an email in `authelia/notification.txt`).

<table>
    <tr>
        <th>Username</th>
        <th>Email</th>
        <th>Password</th>
        <th>Groups</th>
    </tr>
    <tr>
        <td>admin</td>
        <td>admin@localtest.me</td>
        <td>password</td>
        <td>admin</td>
    </tr>
    <tr>
        <td>user1</td>
        <td>user1@localtest.me</td>
        <td>password</td>
        <td>page1</td>
    </tr>
    <tr>
        <td>user2</td>
        <td>user2@localtest.me</td>
        <td>password</td>
        <td>page2</td>
    </tr>
</table>

# Tech stack
<table>
    <tr>
        <th>Name</th>
        <th>Description</th>
    </tr>
    <tr>
        <td><a href="https://github.com/traefik/traefik/">Traefik</a></td>
        <td>Traefik is a modern HTTP reverse proxy and load balancer</td>
    </tr>
    <tr>
        <td><a href="https://www.authelia.com/">Authelia</a></td>
        <td>Authelia is an open-source authentication and authorization server</td>
    </tr>
    <tr>
        <td><a href="https://www.openldap.org/">OpenLDAP</a></td>
        <td>Open source implementation of the Lightweight Directory Access Protocol</td>
    </tr>
    <tr>
        <td><a href="https://phpldapadmin.sourceforge.net/">phpLDAPadmin</a></td>
        <td>Web-based LDAP client. It provides easy administration for your LDAP server.</td>
    </tr>
    <tr>
        <td><a href="https://github.com/FiloSottile/mkcert">mkcert</a></td>
        <td>mkcert is a simple tool for making locally-trusted development certificates.</td>
    </tr>
</table>