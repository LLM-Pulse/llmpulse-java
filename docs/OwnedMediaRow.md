

# OwnedMediaRow

One row of /dimensions/owned_media. Fields depend on provider and view: videos (title, url, channel_name, channel_handle, channel_url, video_id, thumbnail_url, views, published_at), channels (key, name, handle, url, avatar_url, unique_videos), posts (url, caption, owner_handle, thumbnail_url, content_type, likes, comments, views, posted_at), profiles (handle, name, url, avatar_url, followers, unique_posts), own_citations (url, citation_date, position, model), apps (domain, total_responses, rank, global_rank), the Trustpilot views profiles (key, name, rating, reviews_count, url, competitor_id), brands (name, domain, key, rating, rating_change, reviews_count, reviews_held, replied_count, not_replied_count, reply_rate_pct, median_reply_hours, status, url, competitor_id) and reviews (id, brand, rating, title, text, author, published_at, replied, url, competitor_id), and activity (date, entity_id, entity_name, entity_url, yours, citations, plus store and competitor_id where applicable). Activity rows identify a reporting-period start; entity metadata is optional, and entity_id, entity_name and entity_url can be null when unknown. Store and competitor_id appear only where applicable. Every view but own_citations carries citations and yours; videos, channels, posts and profiles carry avg_position.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**date** | **LocalDate** | The start date of the actual reporting period (view&#x3D;activity) |  [optional] |
|**entityId** | **String** | Platform entity identifier (view&#x3D;activity) |  [optional] |
|**entityName** | **String** | Current entity name when known (view&#x3D;activity) |  [optional] |
|**entityUrl** | **String** | Current profile, channel or app listing URL when known (view&#x3D;activity) |  [optional] |
|**store** | [**StoreEnum**](#StoreEnum) | Store selected for provider&#x3D;mobile_apps (view&#x3D;activity) |  [optional] |
|**competitorId** | **Integer** | Competitor identifier when the row represents a competitor&#39;s app or Trustpilot profile |  [optional] |
|**id** | **Integer** | The review&#39;s identifier (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
|**brand** | **String** | The brand or competitor whose Trustpilot profile carries the review (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
|**rating** | **BigDecimal** | Trustpilot rating out of 5: the profile&#39;s at its last monthly read (views profiles and brands) or the review&#39;s stars (view&#x3D;reviews) |  [optional] |
|**ratingChange** | **BigDecimal** | Change of the profile&#39;s rating since the previous monthly read (provider&#x3D;trustpilot, view&#x3D;brands); null before a second read |  [optional] |
|**reviewsCount** | **Integer** | The profile&#39;s review count on Trustpilot at its last monthly read (provider&#x3D;trustpilot) |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | Whether the brand&#39;s Trustpilot profile has been read (found), Trustpilot has no business for its domain (not_found), or it has not been read yet (pending) (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**text** | **String** | The review text (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
|**author** | **String** | The reviewer&#39;s display name (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
|**replied** | **Boolean** | Whether the business replied to the review (provider&#x3D;trustpilot, view&#x3D;reviews) |  [optional] |
|**reviewsHeld** | **Integer** | How many of the profile&#39;s reviews LLM Pulse holds: the newest ones from each monthly read, not every review on Trustpilot (provider&#x3D;trustpilot, view&#x3D;brands). The reply fields count among these, whatever the date window; all of them are null until the profile has been read |  [optional] |
|**repliedCount** | **Integer** | Reviews held that the business replied to (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**notRepliedCount** | **Integer** | Reviews held that the business has not replied to (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**replyRatePct** | **BigDecimal** | replied_count over reviews_held, on a 0-100 scale; null when no review is held (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**medianReplyHours** | **BigDecimal** | Median hours from a held review&#39;s publication to the business&#39;s reply, over the replied reviews held that carry both dates (a reply dated before its review is left out); null when there is none (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**title** | **String** |  |  [optional] |
|**url** | **String** |  |  [optional] |
|**channelName** | **String** |  |  [optional] |
|**channelHandle** | **String** | The video&#39;s channel handle, without the @ |  [optional] |
|**channelUrl** | **String** |  |  [optional] |
|**videoId** | **String** |  |  [optional] |
|**key** | **String** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts; on provider&#x3D;trustpilot, the business domain the profile is filed under, null for a brand without a domain |  [optional] |
|**name** | **String** |  |  [optional] |
|**handle** | **String** |  |  [optional] |
|**caption** | **String** |  |  [optional] |
|**ownerHandle** | **String** |  |  [optional] |
|**thumbnailUrl** | **String** | The post or video image. Our cached copy where one exists, so the link does not expire |  [optional] |
|**avatarUrl** | **String** | The profile or channel image. Our cached copy where one exists |  [optional] |
|**contentType** | **String** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere |  [optional] |
|**citations** | **Integer** | Citations for the row; for view&#x3D;activity, the count in this reporting period |  [optional] |
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
|**domain** | **String** | The app&#39;s store listing URL (provider&#x3D;mobile_apps), or the brand&#39;s domain (provider&#x3D;trustpilot, view&#x3D;brands) |  [optional] |
|**totalResponses** | **Integer** |  |  [optional] |
|**rank** | **Integer** |  |  [optional] |
|**globalRank** | **Integer** |  |  [optional] |



## Enum: StoreEnum

| Name | Value |
|---- | -----|
| GOOGLE_PLAY | &quot;google_play&quot; |
| APP_STORE | &quot;app_store&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| FOUND | &quot;found&quot; |
| NOT_FOUND | &quot;not_found&quot; |
| PENDING | &quot;pending&quot; |



