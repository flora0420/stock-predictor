# Stock Prophet

A demo for stock prophet deployment and hosting with FastAPI and AWS EC2

## Usage
```
curl localhost:8000/ping

curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://localhost:8000/predict
```

## docker setup 
docker run -d --rm --name mycontainer -p 8000:8000 stock-predictor
```
docker images # docker rmi or docker image prune
docker build -t stock-predictor .
docker run -p 8000:8000 stock-predictor  # one can see the log
docker run --rm -p 8000:8000 stock-predictor  # one can see the log
docker run -d --rm --name mycontainer -p 8000:8000 stock-predictor   # behind the scene
docker stop mycontainer 

docker ps -a # docker rm or docker container prune

kill port 
lsof -i :8080

kill -9 pid
```
