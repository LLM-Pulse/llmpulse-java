

# CitedUrlDetailsResponseStats


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**totalResponses** | **Integer** | Answers citing the URL under the filters |  |
|**totalCitations** | **Integer** |  |  |
|**citationRate** | **BigDecimal** | total_responses as a percentage (0-100) of citation_rate_denominator |  |
|**citationRateDenominator** | **Integer** | Answers matching the filters |  |
|**avgCitationPosition** | **BigDecimal** | Null when no visible citation has a rank |  |
|**firstSeenAt** | **OffsetDateTime** | Null when no citation matches the filters |  |
|**lastSeenAt** | **OffsetDateTime** | Null when no citation matches the filters |  |
|**distinctUrls** | **Integer** | Spellings of the URL cited (tracking parameters, a trailing slash) |  |
|**sourceTypes** | [**CitedUrlDetailsResponseStatsSourceTypes**](CitedUrlDetailsResponseStatsSourceTypes.md) |  |  |
|**models** | **Map&lt;String, Integer&gt;** | Answers citing the URL per AI model, keyed by model |  |



