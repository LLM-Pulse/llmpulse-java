

# OwnedMediaProfile


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**url** | **String** |  |  [optional] |
|**handle** | **String** | The handle, page id, store app id, subreddit or username |  [optional] |
|**kind** | [**KindEnum**](#KindEnum) |  |  [optional] |
|**main** | **Boolean** | True for the main profile of its platform (or store), false for an extra one |  [optional] |
|**store** | **String** | google_play or app_store for an app; null elsewhere |  [optional] |
|**name** | **String** |  |  [optional] |
|**avatarUrl** | **String** |  |  [optional] |
|**scrapeStatus** | **String** | State of the profile scrape that reads its name and avatar: pending, running, ready, failed or skipped; null when none has started or the platform has none |  [optional] |



## Enum: KindEnum

| Name | Value |
|---- | -----|
| PROFILE | &quot;profile&quot; |
| APP | &quot;app&quot; |
| SUBREDDIT | &quot;subreddit&quot; |
| USERNAME | &quot;username&quot; |



