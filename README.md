# Stock Predictor

## Chat with Cursor
### Command L to chat
1. Chat: how to build a docker image
2. chat: how to run a container
1. chat: uploda model.py, i changed the code in model.py, do i need to rebuild the image?
3. chat: upload a @Dockerfile  explain  how the WORKDIR and COPY works

### Command K to generate
1. add title to fastapi
2. optimize the code
1. improve typehints & documentation

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
docker run -d --rm --name mycontainer -p 8000:8000 stock-predictor   # behind the scene
docker stop mycontainer 

docker ps -a # docker rm or docker container prune

```
