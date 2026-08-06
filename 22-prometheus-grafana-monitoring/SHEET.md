# 📊 Module 22: Prometheus PromQL & Grafana Monitoring Shortcuts

Quick-reference commands, PromQL metric query formulas, and Grafana dashboard management tricks with practical examples.

---

## 🟢 Level 1: Easy / Beginner Metrics Query Examples

```promql
# 1. Query current CPU load average across all instances
node_load1

# 2. Query total free memory in Bytes
node_memory_MemFree_bytes

# 3. Query HTTP status code counter for API endpoint
http_requests_total{status="200"}
```

---

## 🟡 Level 2: Medium / Intermediate PromQL Query Formulas

```promql
# 1. Calculate per-second rate of HTTP requests over 5 minutes
rate(http_requests_total[5m])

# 2. Calculate CPU usage percentage per instance
100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100)

# 3. Calculate 95th percentile latency from metric histogram
histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))
```

---

## 🔴 Level 3: Hard / Advanced Grafana & Prometheus Administration

```bash
# 1. Run Prometheus in Docker container locally on port 9090
docker run -d -p 9090:9090 --name prometheus -v ./prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus

# 2. Run Grafana in Docker container locally on port 3000
docker run -d -p 3000:3000 --name grafana grafana/grafana

# 3. Reload Prometheus configuration without restarting service
curl -X POST http://localhost:9090/-/reload
```
