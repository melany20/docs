# SkillSortItems
`toloka.client.search_requests.SkillSortItems`

```python
SkillSortItems(self, items=None)
```

Keys for sorting skills in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.SkillSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — The ID of a skill.</li> <li>`&#x27;created&#x27;` — A skill creation date.</li> </ul>

**Examples:**

The example shows how to find skills sorted by creation date in descending order. Skills with equal creation dates are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.SkillSortItems(['-created', 'id'])
result = toloka_client.find_skills(name='Image annotation', sort=sort, limit=10)
```
