

# RecommendationSummary


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**projectId** | **Integer** |  |  |
|**recommendationType** | [**RecommendationTypeEnum**](#RecommendationTypeEnum) |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**errorMessage** | **String** | Set only when status is failed |  |
|**generatedAt** | **OffsetDateTime** | Null until the generation completes |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |
|**totalRecommendations** | **Integer** |  |  |
|**highPriorityCount** | **Integer** |  |  |
|**summary** | [**RecommendationSummarySummary**](RecommendationSummarySummary.md) |  |  |
|**context** | **Object** | Generation context and run diagnostics as stored; empty until the generation completes. Its keys are not a stable contract |  |



## Enum: RecommendationTypeEnum

| Name | Value |
|---- | -----|
| AI_VISIBILITY | &quot;ai_visibility&quot; |
| SOCIAL_COMMUNITY | &quot;social_community&quot; |
| BRAND_BUILDING | &quot;brand_building&quot; |
| SENTIMENT_REPUTATION | &quot;sentiment_reputation&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;pending&quot; |
| PROCESSING | &quot;processing&quot; |
| COMPLETED | &quot;completed&quot; |
| FAILED | &quot;failed&quot; |



