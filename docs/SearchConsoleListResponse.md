

# SearchConsoleListResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | Latest date Google has published for the property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** | Rows in this window (one Google request, at most 25,000) |  [optional] |
|**sort** | **String** |  |  [optional] |
|**startRow** | **Integer** | Present when start_row was set |  [optional] |
|**truncated** | **Boolean** | Present (true) when Google returned 25,000 rows, so more rows exist past this window |  [optional] |
|**data** | [**List&lt;SearchConsoleListResponseDataInner&gt;**](SearchConsoleListResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



