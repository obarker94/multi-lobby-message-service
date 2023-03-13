# Useful

Fresh build of the nginx server is done with:
```
docker build -t mlms-load-balancer .
```

Run the image with:

```
docker run -p 80:80 -d mlms-load-balancer
```
