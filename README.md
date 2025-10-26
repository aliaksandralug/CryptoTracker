import requests

def get_binance_price(symbol: str):
    url = f"https://api.binance.com/api/v3/ticker/price?symbol={symbol.upper()}USDT"
    data = requests.get(url).json()
    return float(data["price"])

def get_coinbase_price(symbol: str):
    url = f"https://api.coinbase.com/v2/prices/{symbol.upper()}-USD/spot"
    data = requests.get(url).json()
    return float(data["data"]["amount"])
