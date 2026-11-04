

# CmsContentSummary


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | WordPress post or page id |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) |  |  [optional] |
|**status** | **String** | WordPress status (publish, future, draft, pending or private) |  [optional] |
|**slug** | **String** |  |  [optional] |
|**title** | **String** | Plain-text title as the site renders it |  [optional] |
|**url** | **String** | The public link on the connected site; null when the site names a link on another host |  [optional] |
|**modifiedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| POST | &quot;post&quot; |
| PAGE | &quot;page&quot; |



