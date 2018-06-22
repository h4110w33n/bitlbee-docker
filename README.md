BitlBee with Plugins on Docker
==============================
A Docker image based on Alpine Linux running BitlBee and a number of plugins. More information about what is contained can be found in the [builder's repo][1].

[1]: https://github.com/h4110w33n/bitlbee-plugins

### Examples

##### Local Only
This will only allow localhost access. Ideal for bouncers like Quassel, ZNC, or for local access.
```
docker run -d --name bitlbee --restart=always \
-v /opt/bitlbee-data:/opt/bitlbee-data:rw \
-v /etc/localtime:/etc/localtime:ro \
-p 127.0.0.1:6667:6667 \
h4110w33n/bitlbee-plugins-docker
```

##### Global
For those who want to run public servers. Not recommended for most users.
```
docker run -d --name bitlbee --restart=always \
-v /opt/bitlbee-data:/opt/bitlbee-data:rw \
-v /etc/localtime:/etc/localtime:ro \
-p 0.0.0.0:6667:6667 \
h4110w33n/bitlbee-plugins-docker
```