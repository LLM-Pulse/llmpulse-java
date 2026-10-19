

# CreateCompetitorRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**brandName** | **String** |  |  |
|**domain** | **String** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) |  |
|**matchingNames** | **List&lt;String&gt;** | Extra names this competitor is matched by; brand_name is added automatically. At most 50 names in all, brand_name included, of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) |  [optional] |
|**citationMatchMode** | [**CitationMatchModeEnum**](#CitationMatchModeEnum) | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path |  [optional] |
|**citationMatchPath** | **String** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored |  [optional] |



## Enum: CitationMatchModeEnum

| Name | Value |
|---- | -----|
| DOMAIN | &quot;domain&quot; |
| HOST | &quot;host&quot; |
| PATH_PREFIX | &quot;path_prefix&quot; |



