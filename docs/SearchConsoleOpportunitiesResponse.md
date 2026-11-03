

# SearchConsoleOpportunitiesResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
|**properties** | [**List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) |  [optional] |
|**excludedProperties** | [**List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them |  [optional] |
|**propertyErrors** | [**List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
|**minImpressions** | **Integer** |  |  [optional] |
|**minPosition** | **BigDecimal** |  |  [optional] |
|**maxPosition** | **BigDecimal** |  |  [optional] |
|**topCtr** | **BigDecimal** | CTR (0..1) of the property&#39;s queries averaging position 3 or better in the window; null when there are none, and then no potential_clicks |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** | Rows in the report before paging |  [optional] |
|**truncated** | **Boolean** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only |  [optional] |
|**data** | [**List&lt;SearchConsoleOpportunitiesResponseDataInner&gt;**](SearchConsoleOpportunitiesResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



