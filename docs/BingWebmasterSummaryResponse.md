

# BingWebmasterSummaryResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**site** | **String** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) |  [optional] |
|**syncStatus** | **String** | State of the daily sync: pending, syncing, completed, failed or on_hold. on_hold means Bing refused the stored API key or the site is no longer verified: the data already synced still answers but stops updating until the site is reconnected in Preferences &gt; Project Settings &gt; Connections. |  [optional] |
|**lastSyncedAt** | **OffsetDateTime** | When the site last synced. Null before its first sync, or while history_current is false. |  [optional] |
|**historyCurrent** | **Boolean** | False right after the site was changed and before its first sync. Until then the response holds no data and data_through is null. |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | The last day synced for the site. Later days are missing, not zero. |  [optional] |
|**totals** | [**BingWebmasterMetrics**](BingWebmasterMetrics.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



