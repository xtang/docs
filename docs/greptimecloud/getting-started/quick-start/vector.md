
The following configuration, written in the `vector.toml` file, collects [host_metrics](https://vector.dev/docs/reference/configuration/sources/host_metrics/) as a Vector source and uses GreptimeCloud as the sink destination.

```toml
[sources.in]
type = "host_metrics"
scrape_interval_secs = 30

[sinks.cloud]
inputs = ["in"]
type = "greptimedb"
endpoint = "<host>:4001"
dbname = "<dbName>"
username = "<username>"
password = "<password>"
```

Then start vector with the specified configuration file:

```shell
vector --config vector.toml
```
