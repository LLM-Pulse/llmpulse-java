

# AiModelInsightsSummaryResponse

One entry per AI model the account has enabled or that answered in the window, in the in-app column order: the models list, which every per-model list and map in summary follows. A share, net sentiment or market share value with nothing behind it is null, because 0 is a real value; counts, totals and weighted visibility scores stay 0.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**filters** | [**AiModelInsightsFiltersEcho**](AiModelInsightsFiltersEcho.md) |  |  [optional] |
|**models** | [**List&lt;AiModelInsightsModel&gt;**](AiModelInsightsModel.md) | The AI models the account has enabled or that answered in the window, in the in-app column order |  [optional] |
|**summary** | [**AiModelInsightsSummaryResponseSummary**](AiModelInsightsSummaryResponseSummary.md) |  |  [optional] |
|**planRequiredFields** | **List&lt;String&gt;** | The summary sections left out because they need a higher plan (brand_net_sentiment_by_model and sentiment_market_share below Growth); empty when none is |  |
|**requestId** | **String** |  |  [optional] |



