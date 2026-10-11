

# SearchConsoleSummaryResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
|**totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
|**dimension** | **String** | Present when a breakdown was requested |  [optional] |
|**breakdown** | [**List&lt;SearchConsoleSummaryResponseBreakdownInner&gt;**](SearchConsoleSummaryResponseBreakdownInner.md) | Present when a breakdown was requested, sorted by impressions descending |  [optional] |
|**breakdownTruncated** | **Boolean** | Present (true) when limit or Google&#39;s 25,000-row maximum left breakdown rows out, so they add up to less than totals |  [optional] |
|**requestId** | **String** |  |  [optional] |



