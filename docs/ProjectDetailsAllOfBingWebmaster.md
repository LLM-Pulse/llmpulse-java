

# ProjectDetailsAllOfBingWebmaster

Bing Webmaster Tools site behind /bing_webmaster. connected means its endpoints answer; reconnect_required means Bing refused the stored API key or the site is no longer verified, so the endpoints still answer from the data already synced, which stops updating until the site is reconnected at connect_url; not_connected means they return ERR_BING_WEBMASTER_NOT_CONNECTED.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**site** | **String** | The connected site (e.g. https://example.com/), null when not connected |  [optional] |
|**lastSyncedAt** | **OffsetDateTime** | When that site last synced, null before its first sync |  [optional] |
|**connectUrl** | **URI** | The in-app page where the site is connected or reconnected (Preferences &gt; Project Settings &gt; Connections) |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |
| NOT_CONNECTED | &quot;not_connected&quot; |



