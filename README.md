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
    uvicorn  main:app --workers 1 --host 0.0.0.0 --port 8000
    ```
    if not working: fnd the path of uvicorn and add it to the path
    ```
    conda env list 

    ~/miniforge3/envs/stocker-neuralprophet/bin/uvicorn main:app --workers 1 --host 0.0.0.0 --port 8000

    ```