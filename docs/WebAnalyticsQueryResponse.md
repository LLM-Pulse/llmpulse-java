

# WebAnalyticsQueryResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**provider** | [**ProviderEnum**](#ProviderEnum) |  |  [optional] |
|**property** | **String** |  |  [optional] |
|**columns** | [**List&lt;WebAnalyticsQueryResponseColumnsInner&gt;**](WebAnalyticsQueryResponseColumnsInner.md) |  |  [optional] |
|**rows** | **List&lt;List&lt;Object&gt;&gt;** | One array per row, values in column order: strings, numbers or null. |  [optional] |
|**rowCount** | **Integer** | Rows in this response (at most 5,000). |  [optional] |
|**totalRows** | **Integer** | Rows the provider has for the query, when it reports it. |  [optional] |
|**truncated** | **Boolean** | True when the provider has more rows than returned; page with its own offset or page field. |  [optional] |
|**totals** | **Map&lt;String, Object&gt;** | Metric totals by metric name, when the query asked for them. |  [optional] |
|**notes** | **List&lt;String&gt;** | Provider caveats: sampling, thresholds, more rows available. |  [optional] |
|**meta** | **Map&lt;String, Object&gt;** | Provider metadata such as GA4 time zone, currency and remaining property quota. |  [optional] |
|**fetchedAt** | **OffsetDateTime** | When the provider answered. |  [optional] |
|**cached** | **Boolean** | True when the answer came from the 10-minute cache instead of the provider. |  [optional] |
|**query** | **Map&lt;String, Object&gt;** | The request as sent to the provider, with the connected property forced and limits applied. |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: ProviderEnum

| Name | Value |
|---- | -----|
| GOOGLE_ANALYTICS | &quot;google_analytics&quot; |
| ADOBE_ANALYTICS | &quot;adobe_analytics&quot; |
| MATOMO | &quot;matomo&quot; |
| POSTHOG | &quot;posthog&quot; |
| PLAUSIBLE | &quot;plausible&quot; |
| PIANO | &quot;piano&quot; |



