

# ProjectDetailsAllOfAiTraffic

Web analytics provider behind /metrics/ai_traffic and /web_analytics. connected means both answer; reconnect_required means the provider refused the stored access, so /metrics/ai_traffic still answers from synced data and /web_analytics returns ERR_WEB_ANALYTICS_ACCESS_REVOKED until it is reconnected at connect_url; not_connected means they return ERR_AI_TRAFFIC_NOT_CONNECTED and ERR_WEB_ANALYTICS_NOT_CONNECTED.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**provider** | **String** | The connected provider (e.g. google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo, piano), null when not connected |  [optional] |
|**connectUrl** | **URI** | The in-app AI Traffic page, where the provider is connected or reconnected |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |
| NOT_CONNECTED | &quot;not_connected&quot; |



