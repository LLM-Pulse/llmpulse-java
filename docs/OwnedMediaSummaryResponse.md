

# OwnedMediaSummaryResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**provider** | **String** |  |  [optional] |
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**connected** | **Boolean** | Whether a profile is claimed on the platform (on overview, on any platform) |  [optional] |
|**kpis** | [**OwnedMediaKpis**](OwnedMediaKpis.md) |  |  [optional] |
|**previous** | [**OwnedMediaSummaryResponsePrevious**](OwnedMediaSummaryResponsePrevious.md) |  |  [optional] |
|**changes** | [**OwnedMediaKpiChanges**](OwnedMediaKpiChanges.md) |  |  [optional] |
|**weekly** | [**List&lt;OwnedMediaWeek&gt;**](OwnedMediaWeek.md) |  |  [optional] |
|**byModel** | [**List&lt;OwnedMediaModelShare&gt;**](OwnedMediaModelShare.md) | Null for provider&#x3D;overview |  [optional] |
|**byCountry** | [**List&lt;OwnedMediaCountryShare&gt;**](OwnedMediaCountryShare.md) | Null for provider&#x3D;overview |  [optional] |
|**contentTypes** | [**List&lt;OwnedMediaContentTypeShare&gt;**](OwnedMediaContentTypeShare.md) | Social and YouTube providers only |  [optional] |
|**ageBuckets** | [**List&lt;OwnedMediaAgeBucketShare&gt;**](OwnedMediaAgeBucketShare.md) | Social and YouTube providers only. Posts or videos without a known publication date are left out |  [optional] |
|**stores** | [**List&lt;OwnedMediaStoreTotals&gt;**](OwnedMediaStoreTotals.md) | provider&#x3D;mobile_apps only |  [optional] |
|**platforms** | [**List&lt;OwnedMediaPlatformRollup&gt;**](OwnedMediaPlatformRollup.md) | provider&#x3D;overview only, one row per platform the caller can read |  [optional] |
|**requestId** | **String** |  |  [optional] |



