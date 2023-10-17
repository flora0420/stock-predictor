# Stock Prophet

Predicting stock prices using neural prophet. 
## Usage
make local prediction
```
conda activate stocker-predictor
python3 app/model.py --ticker MSFT --days 7
```

## local: conda env    
```
conda create --name stocker-predictor python=3.10
conda activate stocker-predictor
pip install -r requirements.txt
```