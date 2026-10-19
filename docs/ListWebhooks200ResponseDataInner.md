

# ListWebhooks200ResponseDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**eventType** | [**EventTypeEnum**](#EventTypeEnum) |  |  [optional] |
|**targetUrl** | **String** | The URL deliveries are sent to. A read-only API key receives only its scheme, host and any non-default port followed by &#x60;/…&#x60; (for example &#x60;https://hook.eu1.make.com/…&#x60;); a &#x60;read_write&#x60; scope key receives the full URL. |  [optional] |
|**disabled** | **Boolean** | True when the subscription receives no more events, including when the API key or OAuth connection that created it was revoked, or when that API key is limited to some projects and no longer covers the subscription&#39;s project. Creating it again with the same project, event and URL replaces it with a new subscription and secret. |  [optional] |
|**failureCount** | **Integer** |  |  [optional] |
|**lastDeliveredAt** | **OffsetDateTime** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |



## Enum: EventTypeEnum

| Name | Value |
|---- | -----|
| MENTION_CREATED | &quot;mention.created&quot; |
| COMPETITOR_MENTION_CREATED | &quot;competitor_mention.created&quot; |
| CITATION_CREATED | &quot;citation.created&quot; |
| PROMPT_EXECUTION_COMPLETED | &quot;prompt_execution.completed&quot; |
| SENTIMENT_NEGATIVE_DETECTED | &quot;sentiment.negative_detected&quot; |
| RECOMMENDATION_COMPLETED | &quot;recommendation.completed&quot; |
| INTELLIGENCE_TASK_COMPLETED | &quot;intelligence_task.completed&quot; |
| INTELLIGENCE_TASK_UPDATED | &quot;intelligence_task.updated&quot; |
| GEO_AUDIT_RUN_COMPLETED | &quot;geo_audit_run.completed&quot; |
| GEO_AUDIT_ALERT_TRIGGERED | &quot;geo_audit_alert.triggered&quot; |



