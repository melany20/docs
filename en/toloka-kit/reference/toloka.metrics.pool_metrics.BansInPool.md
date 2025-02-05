# BansInPool
`toloka.metrics.pool_metrics.BansInPool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/metrics/pool_metrics.py#L426)

```python
BansInPool(
    self,
    pool_id: str,
    count_name: Optional[str] = None,
    filter_by_comment: Optional[Dict[str, str]] = None,
    join_events: bool = False,
    *,
    toloka_client: Optional[TolokaClient] = None,
    atoloka_client: Optional[AsyncTolokaClient] = None,
    timeout: timedelta = ...
)
```

Tracking Toloker restrictions in a pool.


Be careful: if you set in quality controls to ban Tolokers 'on project', bans 'on pool' will never happen.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`pool_id`|**str**|<p>From which pool track metrics.</p>
`count_name`|**Optional\[str\]**|<p>Metric name for a count of bans.</p>
`filter_by_comment`|**Optional\[Dict\[str, str\]\]**|<p>Allow to split Toloker restriction into several lines based on comment. Dictionary where, key - comment string, and value - name for line in which will be aggregated bans with this comments.</p>
`join_events`|**bool**|<p>Count all events in one point. Default False.</p>

**Examples:**

How to collect this metrics:
```python
def print_metric(metric_dict):
    print(metric_dict)

collector = MetricCollector([BansInPool(pool_id, toloka_client=toloka_client)], print_metric)
asyncio.run(collector.run())
```
    'bans_count': [(datetime.datetime(2021, 11, 18, 13, 30, 11, 522000), 1)],
}

How to split bans onto several metrics.
```python
collector = MetricCollector(
    [
        BansInPool(
            pool_id,
            toloka_client=toloka_client,
            filter_by_comment={'fast answers': 'fast', 'bad quality on honeypots': 'honeypots'}
        ),
    ],
    print_metric
)
asyncio.run(collector.run())
```
    'honeypots': [(datetime.datetime(2021, 11, 18, 13, 32, 52, 475000), 1)],
    'fast': [(datetime.datetime(2021, 11, 18, 13, 32, 50, 453000), 1)],
}
## Methods Summary

| Method | Description |
| :------| :-----------|
[get_line_names](toloka.metrics.pool_metrics.BansInPool.get_line_names.md)| Returns a list of metric names that can be generated by this class instance.
