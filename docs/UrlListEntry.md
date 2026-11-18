

# UrlListEntry


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**value** | **String** | The exact URL, \&quot;host/path\&quot; of a prefix, or the host of a domain rule. |  |
|**matchType** | [**MatchTypeEnum**](#MatchTypeEnum) |  |  |
|**host** | **String** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**addedOn** | **LocalDate** |  |  |
|**cost** | **BigDecimal** |  |  |
|**channel** | **String** |  |  |
|**citations** | **Integer** |  |  |
|**citedPages** | **Integer** |  |  |
|**firstCitedAt** | **OffsetDateTime** |  |  |
|**lastCitedAt** | **OffsetDateTime** |  |  |
|**daysToFirstCitation** | **Integer** |  |  |
|**avgCitationPosition** | **BigDecimal** |  |  |
|**models** | **List&lt;String&gt;** |  |  |
|**brandMentioned** | **Boolean** |  |  |



## Enum: MatchTypeEnum

| Name | Value |
|---- | -----|
| URL | &quot;url&quot; |
| PREFIX | &quot;prefix&quot; |
| DOMAIN | &quot;domain&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CITED | &quot;cited&quot; |
| LOST | &quot;lost&quot; |
| NOT_CITED | &quot;not_cited&quot; |



