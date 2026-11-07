

# SearchConsoleAiVisibilityGapsResponseDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**query** | **String** |  |  [optional] |
|**impressions** | **Integer** |  |  [optional] |
|**clicks** | **Integer** |  |  [optional] |
|**ctr** | **BigDecimal** | 0..1 fraction |  [optional] |
|**position** | **BigDecimal** | Impression-weighted average position |  [optional] |
|**promptId** | **Integer** | The project&#39;s prompt the query matches (see match_type); null when no prompt matches |  [optional] |
|**responses** | **Integer** | AI answers the matching prompt got in the window over the account&#39;s enabled models; null when no prompt matches |  [optional] |
|**brandVisibility** | **BigDecimal** | Brand Visibility of the matching prompt in the window, percent (0-100) of its AI answers that mention the brand, over the account&#39;s enabled models; null when no prompt matches or it has no answer |  [optional] |
|**matchType** | **String** | How the query matched: prompt (the same text as the prompt) or fan_out (the same text as a search the prompt&#39;s AI answers ran in the window); null when no prompt matches |  [optional] |



