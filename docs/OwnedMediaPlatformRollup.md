

# OwnedMediaPlatformRollup


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**provider** | [**ProviderEnum**](#ProviderEnum) |  |  [optional] |
|**connected** | **Boolean** |  |  [optional] |
|**total** | **Integer** |  |  [optional] |
|**yours** | **Integer** |  |  [optional] |
|**sharePct** | **BigDecimal** |  |  [optional] |
|**weekly** | [**List&lt;OwnedMediaPlatformRollupWeeklyInner&gt;**](OwnedMediaPlatformRollupWeeklyInner.md) |  |  [optional] |
|**activity** | [**List&lt;OwnedMediaPlatformActivityPeriod&gt;**](OwnedMediaPlatformActivityPeriod.md) | One date/citation row per project tracking period that holds a run inside the window; a period whose runs all fell before from is left out |  [optional] |



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| YOUTUBE | &quot;youtube&quot; |
| MOBILE_APPS | &quot;mobile_apps&quot; |
| INSTAGRAM | &quot;instagram&quot; |
| FACEBOOK | &quot;facebook&quot; |
| TIKTOK | &quot;tiktok&quot; |
| LINKEDIN | &quot;linkedin&quot; |
| TRUSTPILOT | &quot;trustpilot&quot; |
| REDDIT | &quot;reddit&quot; |



