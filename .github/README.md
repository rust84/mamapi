```yaml
services:
  mamapi:
    image: elforkhead/mamapi:latest
    container_name: mamapi
    volumes:
      - ./mamapi/data:/data
    environment:
      - MAM_ID=yourmamapihere
```

Enable debug-level logging:
```yaml
services:
  mamapi:
    environment:
      - DEBUG=True
```

Run behind a gluetun service in the same compose.yaml as mamapi:
```yaml
services:
  mamapi:
    network_mode: "service:gluetun"
```

Run behind a gluetun container that was not started in the same compose.yaml as mamapi:
```yaml
services:
  mamapi:
    network_mode: "container:gluetun"
```