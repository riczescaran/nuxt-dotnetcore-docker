# Nuxt.js + .NET Core + NGINX Reverse Proxy (HTTPS supported)


## Add these to your /etc/hosts

```sh
127.0.0.1 nuxtjs.test
127.0.0.1 dotnetcore.test
```

## Build and run

```sh
docker-compose build && docker-compose up -d
```

## Open the apps
nuxt.js --> http://nuxtjs.test \
dotnetcore --> http://dotnetcore.test

## Enable to access AWS resources
If your apps needs to access AWS resources just simply add in environment:
```
environment:
    AWS_ACCESS_KEY_ID: xxx
    AWS_SECRET_ACCESS_KEY: yyy
    AWS_DEFAULT_REGION: ap-xxx-x
```
## Enable HTTPS
If you want to enable HTTPS, simply modify environments to valid domain and email:

**nuxtjs:**
```
    environment:
        VIRTUAL_HOST: nuxtjs.test
        LETSENCRYPT_HOST: nuxtjs.test
        LETSENCRYPT_EMAIL: your-email@example.com
```

**dotnetcore:**
```
    environment:
        VIRTUAL_HOST: dotnetcore.test
        LETSENCRYPT_HOST: dotnetcore.test
        LETSENCRYPT_EMAIL: your-email@example.com
```
**nginx-proxy-letsencrypt:**
```
    environment:
        DEFAULT_EMAIL: your-email@example.com
```