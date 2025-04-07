instructions and whatnot to come. compose.yml suggestion is below. works well behind gluetun if desired.

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
