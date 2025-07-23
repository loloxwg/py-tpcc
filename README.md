```shell
rm -rf /tmp/tpcc_sqlite*
uv run python -m pytpcc.tpcc  sqlite --warehouses 1 --clients 1 --duration 10
```

```shell
rm -rf /tmp/tpcc_duckdb*
uv run python -m pytpcc.tpcc  duckdb --warehouses 1 --clients 1 --duration 10
```