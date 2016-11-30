docker-transmission
===================

A container dedicated to serve transmission


## Preparation

If you want to build your own image :

```bash
chmod +x files/start
./prepare.sh
```

### Launch

```bash
./launch.sh
```

Example of output:

```
# ./launch.sh
    | Web administration default user created:
    |     Login : transmission
    |     Passwd: rmtjubaG
    | http://<your_server>:9091/

```


Example with Docker Compose:

```
torrent:
  image: stevenmartins/docker-transmission:latest
  environment:
    TRANSMISSION_PASS: "password"
    TRANSMISSION_USER: "zidane"
  volumes:
    - ./data:/transmission/downloads
  ports:
    - "60000:9091"
    - "51413:51413/udp"
    - "51413:51413"
```
