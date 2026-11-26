

# AiModelPositionDistributionBrand


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**type** | **String** | project or competitor |  |
|**id** | **Integer** | Project id, or competitor id |  |
|**competitorId** | **Integer** | Null for the project, the competitor id otherwise |  |
|**name** | **String** |  |  |
|**domain** | **String** | Bare (scheme-less) domain. Null for the project when it has no URL. |  |
|**buckets** | [**List&lt;AiModelPositionDistributionBrandBucketsInner&gt;**](AiModelPositionDistributionBrandBucketsInner.md) | One per position bucket, in order: position_1, position_2_3, position_4_7 and position_8_plus |  |
|**maxStackedValue** | **Integer** | The brand&#39;s largest mentions count of one period, its buckets added up |  |



