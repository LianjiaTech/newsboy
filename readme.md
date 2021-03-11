
### ENV
- Node.js (7.6+)
- MongoDB (2.6+)


### Nginx in dev mode

Don't forget to enable websocket proxy if you use nginx when deploy this service

``` shell
location /
proxy_http_version 1.1;
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection "upgrade";
```

### install

```shell
mkdir api_weapon
cd api_weapon
git clone git@github.com:LianjiaTech/newsboy.git api-weapon
# custom config in config.json
cp api-weapon/config_example.json ./config.json 
cd api-weapon
# install dependencies
npm install
# init mongodb and admin account, also can be set in config.json
npm run install-server
# build client
npm run build-client 
# start server，visit 127.0.0.1:{custom port in config.json }
node server/app.js 
```
