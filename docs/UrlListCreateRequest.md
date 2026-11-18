

# UrlListCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**name** | **String** |  |  |
|**description** | **String** |  |  [optional] |
|**currency** | [**CurrencyEnum**](#CurrencyEnum) |  |  [optional] |
|**entries** | [**List&lt;UrlListEntryInput&gt;**](UrlListEntryInput.md) |  |  [optional] |
|**matchType** | [**MatchTypeEnum**](#MatchTypeEnum) | Read every entry without its own match_type as this type. Default detects it from each value. |  [optional] |



## Enum: CurrencyEnum

| Name | Value |
|---- | -----|
| USD | &quot;USD&quot; |
| EUR | &quot;EUR&quot; |
| GBP | &quot;GBP&quot; |



## Enum: MatchTypeEnum

| Name | Value |
|---- | -----|
| URL | &quot;url&quot; |
| PREFIX | &quot;prefix&quot; |
| DOMAIN | &quot;domain&quot; |



