

# GetAccount200Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**plan** | **String** | Plan key (starter, growth, scale, ...) |  [optional] |
|**planName** | **String** | Display name of the plan to show people (e.g. Scale++ for the scaleplusplus key) |  [optional] |
|**trackingFrequency** | **String** | How often prompts run (weekly, daily, monthly, ...) |  [optional] |
|**role** | [**RoleEnum**](#RoleEnum) | Whether the key belongs to the account owner or a team member |  [optional] |
|**subscription** | [**GetAccount200ResponseSubscription**](GetAccount200ResponseSubscription.md) |  |  [optional] |
|**limits** | [**GetAccount200ResponseLimits**](GetAccount200ResponseLimits.md) |  |  [optional] |
|**rateLimits** | [**GetAccount200ResponseRateLimits**](GetAccount200ResponseRateLimits.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: RoleEnum

| Name | Value |
|---- | -----|
| OWNER | &quot;owner&quot; |
| MEMBER | &quot;member&quot; |



