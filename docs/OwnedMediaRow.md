

# OwnedMediaRow

One row of /dimensions/owned_media. Fields depend on provider and view: videos (title, url, channel_name, channel_handle, channel_url, video_id, thumbnail_url, views, published_at), channels (key, name, handle, url, avatar_url, unique_videos), posts (url, caption, owner_handle, thumbnail_url, content_type, likes, comments, views, posted_at), profiles (handle, name, url, avatar_url, followers, unique_posts), own_citations (url, citation_date, position, model) and apps (domain, total_responses, rank, global_rank). Every view but own_citations carries citations and yours; videos, channels, posts and profiles carry avg_position.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**title** | **String** |  |  [optional] |
|**url** | **String** |  |  [optional] |
|**channelName** | **String** |  |  [optional] |
|**channelHandle** | **String** | The video&#39;s channel handle, without the @ |  [optional] |
|**channelUrl** | **String** |  |  [optional] |
|**videoId** | **String** |  |  [optional] |
|**key** | **String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts |  [optional] |
|**name** | **String** |  |  [optional] |
|**handle** | **String** |  |  [optional] |
|**caption** | **String** |  |  [optional] |
|**ownerHandle** | **String** |  |  [optional] |
|**thumbnailUrl** | **String** | The post or video image. Our cached copy where one exists, so the link does not expire |  [optional] |
|**avatarUrl** | **String** | The profile or channel image. Our cached copy where one exists |  [optional] |
|**contentType** | **String** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere |  [optional] |
|**citations** | **Integer** |  |  [optional] |
|**uniqueVideos** | **Integer** |  |  [optional] |
|**uniquePosts** | **Integer** |  |  [optional] |
|**followers** | **Integer** |  |  [optional] |
|**likes** | **Integer** |  |  [optional] |
|**comments** | **Integer** |  |  [optional] |
|**views** | **Object** | View count as the platform reports it, a number or a numeric string, or null when unknown |  [optional] |
|**publishedAt** | **String** | Publication date as the platform reports it |  [optional] |
|**postedAt** | **String** | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) |  [optional] |
|**avgPosition** | **BigDecimal** | Average position of the citation in the answers (1 &#x3D; first); null when unknown |  [optional] |
|**yours** | **Boolean** |  |  [optional] |
|**citationDate** | **OffsetDateTime** |  |  [optional] |
|**position** | **Integer** |  |  [optional] |
|**model** | **String** |  |  [optional] |
|**domain** | **String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps) |  [optional] |
|**totalResponses** | **Integer** |  |  [optional] |
|**rank** | **Integer** |  |  [optional] |
|**globalRank** | **Integer** |  |  [optional] |



