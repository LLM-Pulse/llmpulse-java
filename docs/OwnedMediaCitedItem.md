

# OwnedMediaCitedItem

The post, video, profile or channel. Null when nothing in the window matches it

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**kind** | [**KindEnum**](#KindEnum) | post covers posts and videos, profile covers profiles and channels |  [optional] |
|**title** | **String** |  |  [optional] |
|**subtitle** | **String** |  |  [optional] |
|**url** | **String** |  |  [optional] |
|**imageUrl** | **String** |  |  [optional] |
|**yours** | **Boolean** |  |  [optional] |
|**date** | **OffsetDateTime** | Publication date of a post or video |  [optional] |
|**stats** | [**OwnedMediaCitedItemStats**](OwnedMediaCitedItemStats.md) |  |  [optional] |



## Enum: KindEnum

| Name | Value |
|---- | -----|
| POST | &quot;post&quot; |
| PROFILE | &quot;profile&quot; |



