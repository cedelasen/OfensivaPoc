# OfensivaPoc

Build image:
```
cd docker
docker build -t ofensiva_poc:1.0.0 -f Dockerfile . 

```

Run in host network to see DetectionLab:

```
docker run -it --network host ofensiva_poc:1.0.0
```
