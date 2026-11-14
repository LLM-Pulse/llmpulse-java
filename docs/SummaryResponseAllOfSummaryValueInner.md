

# SummaryResponseAllOfSummaryValueInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**actor** | [**Actor**](Actor.md) |  |  [optional] |
|**metric** | **String** |  |  [optional] |
|**total** | **BigDecimal** | Count metrics sum the buckets; rate, position and sentiment metrics average them. ai_visibility_score (weighted_visibility) is the window&#39;s points divided by its data days (the days with responses under the filters), the number the app shows, whatever the granularity. |  [optional] |
|**aggregation** | [**AggregationEnum**](#AggregationEnum) | How total combines the buckets (average for ai_visibility_score, a per-data-day score) |  [optional] |
|**min** | **BigDecimal** |  |  [optional] |
|**max** | **BigDecimal** |  |  [optional] |
|**last** | **BigDecimal** |  |  [optional] |



## Enum: AggregationEnum

| Name | Value |
|---- | -----|
| SUM | &quot;sum&quot; |
| AVERAGE | &quot;average&quot; |



