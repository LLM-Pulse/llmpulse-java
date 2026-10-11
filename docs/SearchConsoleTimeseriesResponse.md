

# SearchConsoleTimeseriesResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
|**granularity** | **String** |  |  [optional] |
|**data** | [**List&lt;SearchConsoleTimeseriesResponseDataInner&gt;**](SearchConsoleTimeseriesResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



