# fit
`crowdkit.aggregation.embeddings.rasa.RASA.fit` | [Source code](https://github.com/Toloka/crowd-kit/blob/v1.1.0/crowdkit/aggregation/embeddings/rasa.py#L105)

```python
fit(
    self,
    data: DataFrame,
    true_embeddings: Optional[Series] = None
)
```

Fit the model.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`data`|**DataFrame**|<p>Workers&#x27; outputs with their embeddings. A pandas.DataFrame containing `task`, `worker`, `output` and `embedding` columns.</p>
`true_embeddings`|**Optional\[Series\]**|<p>Tasks&#x27; embeddings. A pandas.Series indexed by `task` and holding corresponding embeddings.</p>

* **Returns:**

  self.

* **Return type:**

  [RASA](crowdkit.aggregation.embeddings.rasa.RASA.md)
