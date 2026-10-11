

# ProjectDetailsAllOfSearchConsole

Google Search Console connection of the project. connected means the Search Console endpoints can answer; reconnect_required means Google refused the stored access and the property must be reconnected in Preferences > Project Settings > Data Connections.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**property** | **String** | The connected property (e.g. sc-domain:example.com), null when not connected |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |
| NOT_CONNECTED | &quot;not_connected&quot; |



