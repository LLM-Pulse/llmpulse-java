

# CreateWebhookRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**eventType** | [**EventTypeEnum**](#EventTypeEnum) |  |  |
|**targetUrl** | **String** | Public HTTPS URL that will receive signed event payloads |  |



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



