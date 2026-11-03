

# AiModelSentimentRow


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**model** | **String** | AI model key, as /dimensions/models lists it |  [optional] |
|**label** | **String** | Display name of the model |  [optional] |
|**color** | **String** | Hex color the app charts the model with |  [optional] |
|**sentimentsCount** | **Integer** | Brand sentiment verdicts in the model&#39;s answers |  [optional] |
|**positiveCount** | **Integer** | Positive and very positive verdicts |  [optional] |
|**negativeCount** | **Integer** | Negative and very negative verdicts |  [optional] |
|**netSentiment** | **BigDecimal** | positive_count minus negative_count as a percentage (-100 to 100) of sentiments_count, neutral verdicts counted in the base; null when sentiments_count is 0 |  [optional] |



