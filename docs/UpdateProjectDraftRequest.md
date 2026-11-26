

# UpdateProjectDraftRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**step** | [**StepEnum**](#StepEnum) |  |  |
|**name** | **String** |  |  [optional] |
|**brandName** | **String** | Defaults to name. Up to 100 characters, the name included when it stands in; finalize refuses a longer one with ERR_INVALID_PARAM |  [optional] |
|**description** | **String** |  |  [optional] |
|**industry** | **List&lt;String&gt;** |  |  [optional] |
|**matchingNames** | **List&lt;String&gt;** | Brand-name variants used to detect mentions (details step). At most 50 names of up to 100 characters each; the step stores the list as sent, and finalize refuses a longer list or name with ERR_INVALID_PARAM (422) |  [optional] |
|**externalIdentifier** | **String** |  |  [optional] |
|**prompts** | **List&lt;String&gt;** | Prompts step, each prompt up to 2,000 bytes of UTF-8 text (about 2,000 characters in English, fewer with accented letters or non-Latin scripts). A longer one returns ERR_INVALID_PARAM with error.meta.reason prompt_too_long and the step stays open |  [optional] |
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



