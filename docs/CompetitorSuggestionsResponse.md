

# CompetitorSuggestionsResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**page** | **Integer** |  |  |
|**perPage** | **Integer** |  |  |
|**total** | **Integer** | Rows matching the filters across every page |  |
|**requestId** | **String** |  |  |
|**basis** | [**BasisEnum**](#BasisEnum) |  |  |
|**discovery** | [**CompetitorDiscoveryState**](CompetitorDiscoveryState.md) |  |  |
|**data** | [**List&lt;CompetitorSuggestion&gt;**](CompetitorSuggestion.md) |  |  |



## Enum: BasisEnum

| Name | Value |
|---- | -----|
| BRANDS | &quot;brands&quot; |
| CITATIONS | &quot;citations&quot; |



