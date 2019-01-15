# Yet another SIP003 plugin for shadowsocks, based on v2ray

## Build

```
sudo apt-get install golang-go
git clone https://github.com/shadowsocks/v2ray-plugin
go get
go build
```

## Usage

See command line args for advanced usages.

### Shadowsocks over websocket (HTTP)

On your server

```
ss-server -c config.json -p 80 --plugin v2ray-plugin --plugin-opts "server"
```

On your client

```
sslocal -c config.json -p 80 --plugin v2ray-plugin
```

### Shadowsocks over websocket (HTTPS)

On your server

```
ssserver -c config.json -p 443 --plugin v2ray-plugin --plugin-opts "server;tls"
```

On your client

```
sslocal -c config.json -p 443 --plugin v2ray-plugin --plugin-opts "tls"
```

### Shadowsocks over quic

On your server

```
ssserver -c config.json -p 443 --plugin v2ray-plugin --plugin-opts "server;mode=quic"
```

On your client

```
sslocal -c config.json -p 443 --plugin v2ray-plugin --plugin-opts "mode=quic"
```
