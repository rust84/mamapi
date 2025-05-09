![Docker Pulls](https://img.shields.io/docker/pulls/elforkhead/mamapi)

General docker compose format:
```yaml
services:
  mamapi:
    image: elforkhead/mamapi:latest
    container_name: mamapi
    restart: unless-stopped
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

Run behind a gluetun service in the same compose as mamapi:
```yaml
services:
  mamapi:
    network_mode: "service:gluetun"
```

Run behind a gluetun container that was not started in the same compose as mamapi:
```yaml
services:
  mamapi:
    network_mode: "container:gluetun"
```

WIP features:
- Associate a given mam_id with ASN of original session, avoid updating API from a different ASN to preserve the session.
- Intelligently select the correct mam_id for a given ASN from a set of mam_ids.
