

# ProjectDetailsAllOfAgentTraffic

Agent traffic source behind /metrics/agent_traffic. connected and reconnect_required (the source refused the stored access, so syncing stopped) both answer from stored data; imported means no live source is connected but imported logs answer; not_connected means it returns ERR_AGENT_TRAFFIC_NOT_CONNECTED.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**provider** | **String** | The connected source (e.g. cloudflare_graphql, bunny_cdn, s3 or the log drain&#39;s provider), null without a live source |  [optional] |
|**connectUrl** | **URI** | The in-app Agent Analytics page, where a source is connected or reconnected |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| CONNECTED | &quot;connected&quot; |
| RECONNECT_REQUIRED | &quot;reconnect_required&quot; |
| IMPORTED | &quot;imported&quot; |
| NOT_CONNECTED | &quot;not_connected&quot; |



