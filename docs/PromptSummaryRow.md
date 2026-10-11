

# PromptSummaryRow


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**promptId** | **Integer** |  |  [optional] |
|**promptText** | **String** |  |  [optional] |
|**model** | **String** | Only present when breakdown&#x3D;model |  [optional] |
|**responses** | **Integer** |  |  [optional] |
|**mentions** | **Integer** |  |  [optional] |
|**citations** | **Integer** |  |  [optional] |
|**visibility** | **BigDecimal** |  |  [optional] |
|**mentionRate** | **BigDecimal** |  |  [optional] |
|**citationRate** | **BigDecimal** |  |  [optional] |
|**avgMentionPosition** | **BigDecimal** |  |  [optional] |
|**avgPosition** | **BigDecimal** |  |  [optional] |
|**appUrl** | **URI** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |  [optional] |
|**countryCode** | **String** | Country of the prompt, as in /dimensions/prompts |  [optional] |
|**languageCode** | **String** | Language of the prompt, as in /dimensions/prompts |  [optional] |
|**promptType** | **String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |  [optional] |
|**brandKind** | **String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |  [optional] |
|**tags** | [**List&lt;TagRef&gt;**](TagRef.md) | Every tag the prompt belongs to |  [optional] |
|**sentimentResponses** | **Integer** | Responses in the window with a sentiment verdict for the brand, the base of the sentiment percentages (deduplicated like the sentiment timeseries) |  [optional] |
|**sentimentVeryPositive** | **BigDecimal** | Percentage (0-100) of sentiment_responses whose brand verdict is very positive; null when sentiment_responses is 0 |  [optional] |
|**sentimentPositive** | **BigDecimal** | Percentage (0-100) of sentiment_responses whose brand verdict is positive; null when sentiment_responses is 0 |  [optional] |
|**sentimentNeutral** | **BigDecimal** | Percentage (0-100) of sentiment_responses whose brand verdict is neutral; null when sentiment_responses is 0 |  [optional] |
|**sentimentNegative** | **BigDecimal** | Percentage (0-100) of sentiment_responses whose brand verdict is negative; null when sentiment_responses is 0 |  [optional] |
|**sentimentVeryNegative** | **BigDecimal** | Percentage (0-100) of sentiment_responses whose brand verdict is very negative; null when sentiment_responses is 0 |  [optional] |
|**netSentiment** | **BigDecimal** | Positive minus negative percentages (-100 to 100), neutral counted in the base; null when sentiment_responses is 0 |  [optional] |



