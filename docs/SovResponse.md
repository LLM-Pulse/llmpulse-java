

# SovResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**granularity** | **String** | day, week or month |  [optional] |
|**filters** | [**MetricsFiltersEcho**](MetricsFiltersEcho.md) |  |  [optional] |
|**periods** | [**List&lt;SovResponsePeriodsInner&gt;**](SovResponsePeriodsInner.md) | Per-bucket sample size and completeness: mentions is the total the shares were computed on (1-3 mentions produce the 100/50/33.33 low-sample patterns); partial marks buckets still collecting data or clipped by the requested window; confidence and margin_of_error read the sample size. |  [optional] |
|**sample** | [**SovResponseSample**](SovResponseSample.md) |  |  [optional] |
|**overTime** | [**List&lt;SovResponseOverTimeInner&gt;**](SovResponseOverTimeInner.md) |  |  [optional] |
|**current** | [**List&lt;SovResponseCurrentInner&gt;**](SovResponseCurrentInner.md) |  |  [optional] |
|**breakdown** | [**List&lt;SovResponseBreakdownInner&gt;**](SovResponseBreakdownInner.md) |  |  [optional] |
|**others** | [**List&lt;SovResponseOthersInner&gt;**](SovResponseOthersInner.md) | Actors ranked fifth and below, folded into the Others share of breakdown |  [optional] |
|**requestId** | **String** |  |  [optional] |



