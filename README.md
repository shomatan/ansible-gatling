# Docker compose: GitBucket + SSL

An example for [GitBucket](https://github.com/gitbucket/gitbucket) with [Let's Encrypt](https://letsencrypt.org/).

## Requirements
- Docker
- docker-compose

## Usage
### Step1: git clone
    git clone https://github.com/shomatan/gitbucket-ssl-docker-compose.git gitbucket-ssl
    cd gitbucket-ssl



### Step2: Edit docker-compose.yml

```diff
     image: shomatan/gitbucket:4.15.0
     environment:
       # nginx-proxy
-      VIRTUAL_HOST: git.example.com
+      VIRTUAL_HOST: YOUR_DOMAIN
       VIRTUAL_PORT: 8080
       # letsencrypt
-      LETSENCRYPT_HOST: git.example.com
-      LETSENCRYPT_EMAIL: git@example.com
+      LETSENCRYPT_HOST: YOUR_DOMAIN
+      LETSENCRYPT_EMAIL: YOUR_EMAIL
       LETSENCRYPT_TEST: "false"
     ports:
       - 29418:29418
```

### Step3: Run services

    docker-compose up -d

You will be able to access sites after a while.

- GitBucket `https://YOUR_DOMAIN`