

# ProjectDetails


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**name** | **String** | Internal project label (sidebar, settings, admin) |  [optional] |
|**brandName** | **String** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. |  [optional] |
|**url** | **URI** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**matchingNames** | **List&lt;String&gt;** |  |  [optional] |
|**additionalOwnedDomains** | **List&lt;String&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none |  [optional] |
|**industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape |  [optional] |
|**businessModel** | **String** |  |  [optional] |
|**businessModelOther** | **String** | Set only when business_model is OTHER |  [optional] |
|**primaryProducts** | **List&lt;String&gt;** |  |  [optional] |
|**targetAudience** | **String** |  |  [optional] |
|**brandVoice** | **String** |  |  [optional] |
|**goals** | **String** |  |  [optional] |
|**countryCode** | **String** |  |  [optional] |
|**languageCode** | **String** |  |  [optional] |
|**paused** | **Boolean** |  |  [optional] |
|**googlePlayId** | **String** |  |  [optional] |
|**appStoreId** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**promptLimit** | **Integer** | Maximum number of active prompts this project may hold, set by the account owner or a co-owner in Account Settings &gt; Prompt Limits; null when the project has no limit of its own and only the account quota applies |  [optional] |
|**stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  |  [optional] |
|**dataCoverage** | [**ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md) |  |  [optional] |
|**searchConsole** | [**ProjectDetailsAllOfSearchConsole**](ProjectDetailsAllOfSearchConsole.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



