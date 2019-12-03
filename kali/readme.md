```
docker build -t kali:latest .
docker run -it --rm -p 80:80 -p 4444:4444 -p 8080:8080 kali:latest
```