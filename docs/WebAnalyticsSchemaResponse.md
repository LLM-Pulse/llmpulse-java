

# WebAnalyticsSchemaResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**provider** | [**ProviderEnum**](#ProviderEnum) | The connected web analytics provider. |  [optional] |
|**property** | **String** | The property, site, report suite (rsid:...), data view (dataview:...) or project every query runs on. |  [optional] |
|**queryLanguage** | **String** | The native query format the provider accepts. |  [optional] |
|**docsUrl** | **String** | The provider&#39;s reference for that format. |  [optional] |
|**allowedFields** | **List&lt;String&gt;** | Top-level query fields that are forwarded. |  [optional] |
|**rules** | **List&lt;String&gt;** | What the bridge enforces and the provider&#39;s main constraints. |  [optional] |
|**example** | **Map&lt;String, Object&gt;** | A worked query to adapt. |  [optional] |
|**fields** | **Map&lt;String, Object&gt;** | The provider&#39;s live field list where it offers one: GA4 dimensions and metrics with custom definitions, Adobe ids, Matomo report methods, PostHog event names, the Plausible catalog. Null when the provider did not return it. |  [optional] |
|**fieldsUnavailable** | **String** | Present when the field list could not be read; the format and example still apply. |  [optional] |
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



