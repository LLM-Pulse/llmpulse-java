

# PromptSummaryResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  |  [optional] |
|**breakdown** | **String** |  |  [optional] |
|**sort** | **String** |  |  [optional] |
|**sortDir** | **String** |  |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** |  |  [optional] |
|**data** | [**List&lt;PromptSummaryRow&gt;**](PromptSummaryRow.md) |  |  [optional] |
|**planRequiredFields** | **List&lt;String&gt;** | The row fields left out because they need a higher plan (the sentiment fields below Growth); empty when none is |  |
|**requestId** | **String** |  |  [optional] |



