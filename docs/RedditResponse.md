

# RedditResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**page** | **Integer** |  |  |
|**perPage** | **Integer** |  |  |
|**total** | **Integer** | Rows matching the filters across every page |  |
|**requestId** | **String** |  |  |
|**view** | **String** | subreddits, authors, threads or breakdowns |  |
|**from** | **OffsetDateTime** | Start of the window, 30 days back by default |  |
|**to** | **OffsetDateTime** |  |  |
|**citations** | **Integer** | Reddit citations after the filters (view&#x3D;breakdowns) |  [optional] |
|**data** | [**List&lt;RedditRow&gt;**](RedditRow.md) |  |  |



