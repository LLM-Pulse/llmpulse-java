

# CmsContentItem


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | WordPress post or page id |  [optional] |
|**type** | [**TypeEnum**](#TypeEnum) |  |  [optional] |
|**status** | **String** | WordPress status (publish, future, draft, pending or private) |  [optional] |
|**slug** | **String** |  |  [optional] |
|**title** | **String** | Plain-text title as the site renders it |  [optional] |
|**url** | **String** | The public link on the connected site; null when the site names a link on another host |  [optional] |
|**modifiedAt** | **OffsetDateTime** |  |  [optional] |
|**excerpt** | **String** | Plain-text excerpt, up to 2,000 characters |  [optional] |
|**contentHtml** | **String** | Sanitized HTML (headings, paragraphs, lists, tables, quotes, code, links with href only), up to 200,000 characters |  [optional] |
|**contentTruncated** | **Boolean** |  |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| POST | &quot;post&quot; |
| PAGE | &quot;page&quot; |



