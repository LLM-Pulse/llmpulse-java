

# CitationGroupRow

A cited URL, domain or host (view). url-view rows carry url, url_sha256 and normalized_url, plus page_cache and page_mentions when page details are included; domain and host rows carry domain or host and aggregate_details.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**sourceId** | **Integer** | The group&#39;s first citation |  |
|**view** | **String** | url, domain or host |  |
|**key** | **String** | The URL as cited, the domain or the host |  |
|**totalResponses** | **Integer** | Answers citing it |  |
|**totalCitations** | **Integer** |  |  |
|**citationRate** | **BigDecimal** | total_responses as a percentage (0-100) of citation_rate_denominator |  |
|**citationRateDenominator** | **Integer** | Answers matching the filters |  |
|**avgCitationPosition** | **BigDecimal** | Null when no visible citation has a rank |  |
|**firstSeenAt** | **OffsetDateTime** |  |  |
|**lastSeenAt** | **OffsetDateTime** |  |  |
|**models** | **Map&lt;String, Integer&gt;** | Answers citing it per AI model, keyed by model |  |
|**url** | **String** | url view only. The URL as cited |  [optional] |
|**urlSha256** | **String** | url view only. Key of the cited page, shared by the URL&#39;s variants |  [optional] |
|**normalizedUrl** | **String** | url view only |  [optional] |
|**pageCache** | [**CitationPageCache**](CitationPageCache.md) |  |  [optional] |
|**pageMentions** | [**CitationPageMentions**](CitationPageMentions.md) |  |  [optional] |
|**domain** | **String** | domain view only |  [optional] |
|**host** | **String** | host view only |  [optional] |
|**aggregateDetails** | [**CitationGroupRowAggregateDetails**](CitationGroupRowAggregateDetails.md) |  |  [optional] |
|**citationSeries** | [**CitationSeries**](CitationSeries.md) |  |  [optional] |



