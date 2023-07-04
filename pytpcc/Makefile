
.PHONY: dep config mock run  clean

WAREHOUSES ?= 100

dep:
	pip install -r requirements.txt

config:
	python tpcc.py --print-config duckdb > /tmp/duckdb.config

mock:
	python tpcc.py --no-execute --config=/tmp/duckdb.config --warehouses=${WAREHOUSES}  --ddl=duckdb.sql duckdb
	

run:
	python tpcc.py --no-load --config=/tmp/duckdb.config  --warehouses=${WAREHOUSES}  duckdb




