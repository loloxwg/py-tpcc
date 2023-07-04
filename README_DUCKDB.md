# Duckdb TPCC Python Driver

## Prequistes
Make sure Python 3.8 or higher is installed
pip install duckdb==0.8.1
pip install numpy

## How to mock TPC-C data

1. Clone py-tpcc repository
   ```shell
   $ git clone <py-tpcc repo https/ssh url>
   ```
2. Install dependencies
   ```shell
   $ cd pytpcc
   $ pip install -r requirements.txt
   ```
3. Generate duckdb driver config file
   ```shell
   $ python tpcc.py --print-config duckdb > /tmp/duckdb.config
   ```
4. Modify config file to specify the db path
   ```shell
   $ database = /tmp/duckdb.tpcc
   ```
5. Mock data
   ```shell
   $ python tpcc.py --no-execute --config=/tmp/duckdb.config --warehouses=1 --ddl=duckdb.sql duckdb
   ```

## How to run TPC-C

1. Follow above steps to load data
2. Execute
   ```shell
   $ python tpcc.py --no-load --config=/tmp/duckdb.config --warehouses=1 duckdb
   ```
