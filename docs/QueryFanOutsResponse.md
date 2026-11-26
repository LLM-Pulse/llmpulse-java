

# QueryFanOutsResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**page** | **Integer** |  |  |
|**perPage** | **Integer** |  |  |
|**total** | **Integer** | Rows matching the filters across every page |  |
|**requestId** | **String** |  |  |
|**view** | **String** | query or prompt, the row shape of data |  |
|**totalOccurrences** | **Integer** | Sub-query occurrences across every page (view&#x3D;query) |  [optional] |
|**data** | [**List&lt;QueryFanOutRow&gt;**](QueryFanOutRow.md) |  |  |



