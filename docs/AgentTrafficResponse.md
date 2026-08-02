

# AgentTrafficResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**groupBy** | [**GroupByEnum**](#GroupByEnum) |  |  [optional] |
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  [optional] |
|**totals** | **Map&lt;String, Integer&gt;** |  |  [optional] |
|**timeseries** | **Map&lt;String, Map&lt;String, Integer&gt;&gt;** |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: GroupByEnum

| Name | Value |
|---- | -----|
| BOT | &quot;bot&quot; |
| COMPANY | &quot;company&quot; |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



