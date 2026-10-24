

# UpdateRecommendationItemRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) | completed, archived, or active to restore the item |  |
|**reason** | [**ReasonEnum**](#ReasonEnum) | Optional, with status archived only. competitor only on a PR &amp; Citation Building item that targets a domain. |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| COMPLETED | &quot;completed&quot; |
| ARCHIVED | &quot;archived&quot; |



## Enum: ReasonEnum

| Name | Value |
|---- | -----|
| NOT_RELEVANT | &quot;not_relevant&quot; |
| TOO_COMPLEX | &quot;too_complex&quot; |
| COMPETITOR | &quot;competitor&quot; |



