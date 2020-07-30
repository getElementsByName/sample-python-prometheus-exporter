### prometheus exporter
- https://github.com/prometheus/client_python


### 설명
커스텀으로 구축하는 경우 아래와 같은 prometheus 플랫폼을 활용하는 export 서버를 만들면 비교적 간단하게 metric을 수집하고 시각화 할 수 있음

```python
# Create a metric to track time spent and requests made.
REQUEST_TIME = Summary('request_processing_seconds', 'Time spent processing request')

# Decorate function with metric.
@REQUEST_TIME.time()
def process_request(t):
```

```sh
# HELP request_processing_seconds Time spent processing request
# TYPE request_processing_seconds summary
request_processing_seconds_count 253.0
request_processing_seconds_sum 126.53607600694522

# HELP request_processing_seconds_created Time spent processing request
# TYPE request_processing_seconds_created gauge
request_processing_seconds_created 1.596114494196529e+09
```