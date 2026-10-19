

# UpdateProjectDraftRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**step** | [**StepEnum**](#StepEnum) |  |  |
|**name** | **String** |  |  [optional] |
|**brandName** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**industry** | **List&lt;String&gt;** |  |  [optional] |
|**matchingNames** | **List&lt;String&gt;** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) |  [optional] |
|**externalIdentifier** | **String** |  |  [optional] |
|**prompts** | **List&lt;String&gt;** |  |  [optional] |
|**competitors** | **List&lt;Object&gt;** | Competitors step: objects {domain, brand_name, matching_names}, capped by plan. Each competitor&#39;s matching_names takes at most 50 names of up to 100 characters, checked at finalize like POST /projects |  [optional] |
|**youtubeChannelUrl** | **String** |  |  [optional] |
|**instagramProfileUrl** | **String** |  |  [optional] |
|**facebookPageUrl** | **String** |  |  [optional] |
|**tiktokProfileUrl** | **String** |  |  [optional] |
|**appStoreUrl** | **String** |  |  [optional] |
|**googlePlayUrl** | **String** |  |  [optional] |
|**suggest** | **Boolean** |  |  [optional] |



## Enum: StepEnum

| Name | Value |
|---- | -----|
| DETAILS | &quot;details&quot; |
| PROMPTS | &quot;prompts&quot; |
| COMPETITORS | &quot;competitors&quot; |
| OWNED_MEDIA | &quot;owned_media&quot; |



