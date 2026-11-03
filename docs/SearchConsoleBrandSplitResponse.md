

# SearchConsoleBrandSplitResponse


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
|**brandTerms** | **List&lt;String&gt;** | The project&#39;s brand name, matching names, app names and domain, lowercased, each matched as a whole word |  [optional] |
|**totals** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
|**branded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
|**nonBranded** | [**SearchConsoleMetrics**](SearchConsoleMetrics.md) |  |  [optional] |
|**unclassified** | [**SearchConsoleBrandSplitResponseUnclassified**](SearchConsoleBrandSplitResponseUnclassified.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



