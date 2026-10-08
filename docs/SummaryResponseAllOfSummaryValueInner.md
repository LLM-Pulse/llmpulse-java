

# SummaryResponseAllOfSummaryValueInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**actor** | [**Actor**](Actor.md) |  |  [optional] |
|**metric** | **String** |  |  [optional] |
|**total** | **BigDecimal** |  |  [optional] |
|**aggregation** | [**AggregationEnum**](#AggregationEnum) | How total combines the buckets |  [optional] |
|**min** | **BigDecimal** |  |  [optional] |
|**max** | **BigDecimal** |  |  [optional] |
|**last** | **BigDecimal** |  |  [optional] |



## Enum: AggregationEnum

| Name | Value |
|---- | -----|
| SUM | &quot;sum&quot; |
| AVERAGE | &quot;average&quot; |



