

# CitationPageCache

What was read on the cited page. Metadata is null when the page has no usable content.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**present** | **Boolean** | Whether the page has a saved copy |  |
|**lastCrawledAt** | **OffsetDateTime** | When the saved copy was read; null without usable content |  |
|**statusCode** | **Integer** | A saved successful response or an observed 404/410; null otherwise |  |
|**errorMessage** | **String** | Always null; crawl errors are not exposed |  |
|**contentFormat** | **String** |  |  |
|**bytes** | **Integer** |  |  |
|**htmlTitle** | **String** |  |  |
|**metaTitle** | **String** |  |  |
|**metaDescription** | **String** |  |  |
|**h1** | **String** |  |  |
|**canonicalUrl** | **String** |  |  |
|**language** | **String** |  |  |
|**mentionsProcessed** | **Boolean** | Whether the page&#39;s mention analysis has completed for this project |  |
|**contentAvailable** | **Boolean** |  |  |



