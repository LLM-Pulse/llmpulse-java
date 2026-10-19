

# UpdateCompetitorRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**brandName** | **String** |  |  [optional] |
|**domain** | **String** | Website domain or host used for citation matching. A full URL is accepted and normalised to its host. |  [optional] |
|**matchingNames** | **List&lt;String&gt;** | FULL replacement list of the names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing in the request is applied |  [optional] |
|**color** | **String** | Hex color, e.g. #1a2b3c |  [optional] |
|**citationMatchMode** | [**CitationMatchModeEnum**](#CitationMatchModeEnum) |  |  [optional] |
|**citationMatchPath** | **String** | Required when changing citation_match_mode to path_prefix |  [optional] |



## Enum: CitationMatchModeEnum

| Name | Value |
|---- | -----|
| DOMAIN | &quot;domain&quot; |
| HOST | &quot;host&quot; |
| PATH_PREFIX | &quot;path_prefix&quot; |



