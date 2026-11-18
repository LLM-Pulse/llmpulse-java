

# UrlListWithStats


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**name** | **String** |  |  |
|**description** | **String** |  |  |
|**currency** | [**CurrencyEnum**](#CurrencyEnum) | The currency of the entry costs. |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |
|**entriesCount** | **Integer** |  |  |
|**citedEntries** | **Integer** | Entries an AI answer cited in the window. |  |
|**citations** | **Integer** | AI answers citing any entry in the window, each once. |  |
|**lastCitedAt** | **OffsetDateTime** | The latest answer citing an entry, up to the window&#39;s end. |  |



## Enum: CurrencyEnum

| Name | Value |
|---- | -----|
| USD | &quot;USD&quot; |
| EUR | &quot;EUR&quot; |
| GBP | &quot;GBP&quot; |



