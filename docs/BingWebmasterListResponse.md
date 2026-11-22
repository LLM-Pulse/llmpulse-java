

# BingWebmasterListResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**site** | **String** | The connected site, as Bing Webmaster Tools names it (e.g. https://example.com/) |  [optional] |
|**syncStatus** | **String** | State of the daily sync: pending, syncing, completed, failed or on_hold (the data already synced still answers, but stops updating until the site is reconnected) |  [optional] |
|**lastSyncedAt** | **OffsetDateTime** | When the site last synced. Null before its first sync, or while history_current is false. |  [optional] |
|**historyCurrent** | **Boolean** | False right after the site was changed and before its first sync. Until then data is empty and data_through is null. |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | The last week_ending synced for the site (the Friday that closes a Bing week) |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** | Distinct pages or queries found in the weeks of the window |  [optional] |
|**sort** | **String** |  |  [optional] |
|**weeksCovered** | **Integer** | Weeks with data whose week_ending falls in the window |  [optional] |
|**data** | [**List&lt;BingWebmasterListResponseDataInner&gt;**](BingWebmasterListResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



