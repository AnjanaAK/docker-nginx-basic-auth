# Docker Nginx Proxy with Basic Auth

Simple HTTP Proxy docker container setup using Nginx with Basic Authentication.

```
       username:password      +---------------------------------------+      +---------------------------+
User -----------------------> | Nginx proxy container with basic auth | ---> | HTTP Web Server container |
                              +---------------------------------------+      +---------------------------+
```

The `./nginx/.htpasswd` file was created using the following command:

```bash
$ htpasswd -c ./nginx/.htpasswd user

# enter the password 'pass' here two times
New password:
Re-type new password:
Adding password for user user
```

## Run

```bash
$ docker-compose up -d
```

Confirm if it is working fine by visiting the url in browser:
http://localhost:8080/

```bash
Username: user
Password: pass
```

Also, you can use Curl in command line for the same purpose:
```bash
$ curl -u user:pass http://localhost:8080/
```

## Clean-up

Run the following command to destroy the containers:
```bash
$ docker-compose down
```
