

# AiOrdersResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**platform** | **String** |  |  |
|**currency** | **String** | ISO 4217 code of the most recent stored day; null when the window holds no stored order |  |
|**from** | **LocalDate** |  |  |
|**to** | **LocalDate** |  |  |
|**totals** | [**AiOrdersResponseTotals**](AiOrdersResponseTotals.md) |  |  |
|**bySource** | [**List&lt;AiOrdersResponseBySourceInner&gt;**](AiOrdersResponseBySourceInner.md) | One row per AI assistant, highest revenue first |  |
|**series** | [**List&lt;AiOrdersResponseSeriesInner&gt;**](AiOrdersResponseSeriesInner.md) | Days that have stored orders, oldest first |  |
|**requestId** | **String** |  |  |



