General docker compose format:
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


Upcoming features:
- Add a ~15 day forced requery in case these sessions expire eventually
- May add an optional fix for logging timezone
