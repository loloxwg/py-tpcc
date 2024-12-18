# Duckdb TPCC Python Driver

## Prequistes
Make sure Python 3.8 or higher is installed
```shell
pip install sqlite
pip install numpy
sudo apt install sqlite3
```
pip install sqlite
pip install numpy
sudo apt install sqlite3

## How to mock TPC-C data

1. Install dependencies
```shell
cd pytpcc
pip install -r requirements.txt
```
2. Generate duckdb driver config file
```shell
python tpcc.py --print-config sqlite > /tmp/sqlite.config
```
3. Modify config file to specify the db path
```shell
vim /tmp/sqlite.config
database = /tmp/sqlite/tpcc.db
```
4. Load data
```shell
python tpcc.py --no-execute --config=/tmp/sqlite.config --warehouses=1 --ddl=duckdb.sql sqlite
```

## How to run TPC-C

1. Follow above steps to load data
2. Execute
```shell
python tpcc.py --no-load --config=/tmp/sqlite.config --warehouses=1 sqlite
```
