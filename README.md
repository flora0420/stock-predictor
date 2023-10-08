---
title: StockPredictor
emoji: 🌍
colorFrom: red
colorTo: green
sdk: docker
pinned: false
license: mit
---

Check out the configuration reference at https://huggingface.co/docs/hub/spaces-config-reference


# Stock Prophet

A demo for stock prophet deployment on huggingface spaces

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
docker run -d --rm --name mycontainer -p 8000:8000 stock-prophet
```
docker images # docker rmi or docker image prune
docker build -t stock-neuralprophet .
docker run -p 8000:8000 stock-neuralprophet  # one can see the log
docker run -d --rm --name mycontainer -p 8000:8000 stock-neuralprophet   # behind the scene
```
