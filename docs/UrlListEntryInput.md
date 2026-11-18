

# UrlListEntryInput

An entry. A plain string is read as its value.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**value** | **String** | An exact URL, a \&quot;host/path/_*\&quot; prefix or a domain. |  |
|**matchType** | [**MatchTypeEnum**](#MatchTypeEnum) |  |  [optional] |
|**addedOn** | **LocalDate** | When the URL was published or bought. Default today. |  [optional] |
|**cost** | **BigDecimal** | What the URL cost, in the list currency. |  [optional] |
|**channel** | **String** | Where it came from, such as a marketplace or PR agency. |  [optional] |



## Enum: MatchTypeEnum

| Name | Value |
|---- | -----|
| URL | &quot;url&quot; |
| PREFIX | &quot;prefix&quot; |
| DOMAIN | &quot;domain&quot; |



