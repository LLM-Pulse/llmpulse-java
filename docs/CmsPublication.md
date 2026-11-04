

# CmsPublication


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**platform** | [**PlatformEnum**](#PlatformEnum) |  |  [optional] |
|**siteUrl** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | queued and sending are on their way; unknown means a send timed out and the next attempt looks the draft up before creating one; drafted carries remote_id and edit_url; failed carries error_code |  [optional] |
|**title** | **String** |  |  [optional] |
|**slug** | **String** |  |  [optional] |
|**sourceUrl** | **String** | For an update task, the page the draft revises |  [optional] |
|**remoteId** | **Integer** | WordPress post id of the draft |  [optional] |
|**remoteStatus** | **String** | WordPress status of the post when the draft was created (draft) |  [optional] |
|**remoteUrl** | **String** |  |  [optional] |
|**editUrl** | **String** | The post&#39;s edit screen in the WordPress admin |  [optional] |
|**errorCode** | **String** | Why the send failed, for example reconnect_required, missing_capability, unreachable or rejected |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**sentAt** | **OffsetDateTime** |  |  [optional] |



## Enum: PlatformEnum

| Name | Value |
|---- | -----|
| WORDPRESS | &quot;wordpress&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| SENDING | &quot;sending&quot; |
| UNKNOWN | &quot;unknown&quot; |
| DRAFTED | &quot;drafted&quot; |
| FAILED | &quot;failed&quot; |



