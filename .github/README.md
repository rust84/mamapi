![Docker Pulls](https://img.shields.io/docker/pulls/elforkhead/mamapi)

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
      - TZ=Etc/UTC #https://en.wikipedia.org/wiki/List_of_tz_database_time_zones
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