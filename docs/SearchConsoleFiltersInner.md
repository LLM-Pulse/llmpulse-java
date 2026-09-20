

# SearchConsoleFiltersInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**dimension** | [**DimensionEnum**](#DimensionEnum) |  |  |
|**operator** | [**OperatorEnum**](#OperatorEnum) |  |  [optional] |
|**expression** | **String** |  |  |



## Enum: DimensionEnum

| Name | Value |
|---- | -----|
| COUNTRY | &quot;country&quot; |
| DEVICE | &quot;device&quot; |
| PAGE | &quot;page&quot; |
| QUERY | &quot;query&quot; |
| SEARCH_APPEARANCE | &quot;searchAppearance&quot; |



## Enum: OperatorEnum

| Name | Value |
|---- | -----|
| CONTAINS | &quot;contains&quot; |
| EQUALS | &quot;equals&quot; |
| NOT_CONTAINS | &quot;notContains&quot; |
| NOT_EQUALS | &quot;notEquals&quot; |
| INCLUDING_REGEX | &quot;includingRegex&quot; |
| EXCLUDING_REGEX | &quot;excludingRegex&quot; |



