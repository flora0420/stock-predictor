# Stock Prophet

A demo for stock predictor ( via neuralprophet ) deployment with FastAPI and Docker

## Usage
```
curl localhost:8000/ping
    
curl \
--header "Content-Type: application/json" \
--request POST \
--data '{"ticker":"MSFT", "days":7}' \
http://localhost:8000/predict
```

```
curl -X 'POST' \
  'http://127.0.0.1:8000/predict' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{"ticker": "AAPL", "days": 7}'
```


## local setup
1. conda env    

    ```
    conda create --name stock-neuralprophet python=3.10
    conda activate stock-neuralprophet
    pip install -r requirements.txt
    ```

1. uvicorn 
    ```
    cd app
    uvicorn  main:app --reload --host 0.0.0.0 --port 8000
    ```
    if not working: fnd the path of uvicorn and add it to the path
    ```
    conda env list 

    ~/miniforge3/envs/stocker-neuralprophet/bin/uvicorn main:app --reload --host 0.0.0.0 --port 8000

    ```
1. process

This will check processes using port :8000. If you are using different port for fastAPI then change the port number.
```
lsof -i :8000
```
If you want to kill the process using port :8000
```
kill -9 <PID>
```