

# UpdatePromptRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**promptType** | [**PromptTypeEnum**](#PromptTypeEnum) | Search intent |  [optional] |
|**brandKind** | [**BrandKindEnum**](#BrandKindEnum) | Brand focus: brand (your own brand or products), brand_other (competing brands), non_brand (generic) |  [optional] |



## Enum: PromptTypeEnum

| Name | Value |
|---- | -----|
| INFORMATIONAL | &quot;informational&quot; |
| NAVIGATIONAL | &quot;navigational&quot; |
| COMMERCIAL | &quot;commercial&quot; |
| TRANSACTIONAL | &quot;transactional&quot; |



## Enum: BrandKindEnum

| Name | Value |
|---- | -----|
| BRAND | &quot;brand&quot; |
| BRAND_OTHER | &quot;brand_other&quot; |
| NON_BRAND | &quot;non_brand&quot; |



