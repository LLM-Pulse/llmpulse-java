

# RecommendationItem

One recommendation item, in the shape GET /recommendations/{id} lists items

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**recommendationId** | **Integer** |  |  |
|**recommendationType** | **String** |  |  |
|**category** | **String** |  |  |
|**title** | **String** |  |  |
|**description** | **String** |  |  [optional] |
|**priority** | [**PriorityEnum**](#PriorityEnum) |  |  |
|**estimatedImpact** | **String** |  |  [optional] |
|**actionItems** | **List&lt;String&gt;** |  |  |
|**sourceRefs** | **List&lt;String&gt;** | Evidence codes (e.g. P1, C2) resolved in resolved_source_refs |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**statusChangedAt** | **OffsetDateTime** |  |  [optional] |
|**position** | **Integer** |  |  |
|**metadata** | **Map&lt;String, Object&gt;** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |
|**resolvedSourceRefs** | **List&lt;Map&lt;String, Object&gt;&gt;** | The evidence each source_refs code points to (prompt, citation or own page) |  [optional] |
|**unresolvedSourceRefs** | **List&lt;String&gt;** | Present only when a code points to no stored evidence |  [optional] |



## Enum: PriorityEnum

| Name | Value |
|---- | -----|
| HIGH | &quot;high&quot; |
| MEDIUM | &quot;medium&quot; |
| LOW | &quot;low&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| COMPLETED | &quot;completed&quot; |
| ARCHIVED | &quot;archived&quot; |



