

# ListWebhooks200ResponseDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**eventType** | [**EventTypeEnum**](#EventTypeEnum) |  |  [optional] |
|**targetUrl** | **String** |  |  [optional] |
|**disabled** | **Boolean** |  |  [optional] |
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



