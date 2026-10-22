

# ProjectDetailsAllOfSearchConsole

Google Search Console connection of the project. connected means the Search Console endpoints can answer; reconnect_required means Google refused the stored access, so the endpoints return ERR_SEARCH_CONSOLE_ACCESS_REVOKED until the property is reconnected at connect_url; not_connected means the endpoints return ERR_SEARCH_CONSOLE_NOT_CONNECTED.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**property** | **String** | The connected property (e.g. sc-domain:example.com), null when not connected |  [optional] |
|**connectUrl** | **URI** | The in-app page where the property is connected or reconnected (Preferences &gt; Project Settings &gt; Data Connections) |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |
| NOT_CONNECTED | &quot;not_connected&quot; |



