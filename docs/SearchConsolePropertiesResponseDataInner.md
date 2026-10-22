

# SearchConsolePropertiesResponseDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **String** | Property id, the value the property parameter takes, e.g. sc-domain:example.com |  [optional] |
|**name** | **String** |  |  [optional] |
|**primary** | **Boolean** | The property read when the property parameter is omitted |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**lastSyncedAt** | **OffsetDateTime** |  |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| DOMAIN | &quot;domain&quot; |
| URL_PREFIX | &quot;url_prefix&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |



