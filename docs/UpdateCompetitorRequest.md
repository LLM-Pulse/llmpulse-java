

# UpdateCompetitorRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**brandName** | **String** |  |  [optional] |
|**domain** | **String** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. |  [optional] |
|**matchingNames** | **List&lt;String&gt;** |  |  [optional] |
|**color** | **String** | Hex color, e.g. #1a2b3c |  [optional] |
|**citationMatchMode** | [**CitationMatchModeEnum**](#CitationMatchModeEnum) |  |  [optional] |
|**citationMatchPath** | **String** | Required when changing citation_match_mode to path_prefix |  [optional] |



## Enum: CitationMatchModeEnum

| Name | Value |
|---- | -----|
| DOMAIN | &quot;domain&quot; |
| HOST | &quot;host&quot; |
| PATH_PREFIX | &quot;path_prefix&quot; |



