

# RecommendationLaunchResponseRecommendation


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Poll GET /recommendations/{id} with it |  |
|**recommendationType** | [**RecommendationTypeEnum**](#RecommendationTypeEnum) |  |  |
|**status** | **String** | Always pending |  |
|**createdAt** | **OffsetDateTime** |  |  |



## Enum: RecommendationTypeEnum

| Name | Value |
|---- | -----|
| AI_VISIBILITY | &quot;ai_visibility&quot; |
| SOCIAL_COMMUNITY | &quot;social_community&quot; |
| BRAND_BUILDING | &quot;brand_building&quot; |
| SENTIMENT_REPUTATION | &quot;sentiment_reputation&quot; |



