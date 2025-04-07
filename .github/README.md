instructions and whatnot to come. compose.yml suggestion is below. works well behind gluetun if desired.

feel free to add your time zone code (https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

```yaml
mamapi:
  image: elforkhead/mamapi:latest
  container_name: mamapi
  volumes:
    - ./mamapi/data:/data
  environment:
    - MAM_ID=yourmamidhere
```