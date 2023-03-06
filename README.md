# xiaomi-air-quality-monitor-to-mqtt

## Usage in docker compose

```yaml
version: '3.2'
services:
  xiaomi-air-quality-monitor-to-mqtt:
    container_name: xaqm
    image: rzarajczyk/xiaomi-air-quality-monitor-to-mqtt:latest
    volumes:
      - ./config/xiaomi-air-quality-monitor-to-mqtt.yaml:/app/config/config.yaml
    restart: unless-stopped
    network_mode: host
```

## Configuration

```yaml
mqtt:
  broker: <hostname>
  port: <port>
  username: <username>
  password: <passqord>

xiaomi-air-quality-monitor:
  fetch-interval-seconds: 5  # how often should the Monitor be pulled
  id: xiaomi-air-monitor   # how will the device be identified in MQTT  
  ip: <device IP>
  token: <device token>

```