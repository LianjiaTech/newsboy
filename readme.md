
### ENV
- Node.js (7.6+)
- MongoDB (2.6+)


### Nginx in dev mode

Don't forget to enable websocket proxy if you use nginx when deploy this service

``` shell
在location /
proxy_http_version 1.1;
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection "upgrade";
```

### install

```shell
mkdir api_weapon
cd api_weapon
git clone git@repo vendors 
cp vendors/config_example.json ./config.json //custom config in config.json
cd vendors
npm install
npm run install-server // init mongodb and admin account, also can be set in config.json
npm run build-client // build client
node server/app.js // start server，visit 127.0.0.1:{custom port in config.json }
```
