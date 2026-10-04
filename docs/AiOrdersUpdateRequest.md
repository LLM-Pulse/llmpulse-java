

# AiOrdersUpdateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**platform** | [**PlatformEnum**](#PlatformEnum) |  |  |
|**currency** | **String** | ISO 4217 code, e.g. EUR |  |
|**from** | **LocalDate** | First day of the window this push replaces |  |
|**to** | **LocalDate** | Last day of the window; at most 400 days after from |  |
|**days** | [**List&lt;AiOrdersUpdateRequestDaysInner&gt;**](AiOrdersUpdateRequestDaysInner.md) |  |  |



## Enum: PlatformEnum

| Name | Value |
|---- | -----|
| SHOPIFY | &quot;shopify&quot; |



