

# IntelligenceTaskCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**taskType** | [**TaskTypeEnum**](#TaskTypeEnum) | product_listing is API-only: it needs product and returns ready-to-apply product page copy |  |
|**promptId** | **Integer** | Not used by product_listing; send null or omit it |  [optional] |
|**customTopic** | **String** |  |  [optional] |
|**userInstructions** | **String** |  |  [optional] |
|**outputLanguageCode** | **String** |  |  [optional] |
|**existingContent** | **String** |  |  [optional] |
|**existingContentUrl** | **URI** |  |  [optional] |
|**product** | [**IntelligenceTaskProduct**](IntelligenceTaskProduct.md) |  |  [optional] |
|**promptIds** | **List&lt;Integer&gt;** | product_listing only: up to 20 project prompts the copy should answer |  [optional] |



## Enum: TaskTypeEnum

| Name | Value |
|---- | -----|
| BRIEF | &quot;brief&quot; |
| CREATE | &quot;create&quot; |
| UPDATE | &quot;update&quot; |
| PR_INSIGHTS | &quot;pr_insights&quot; |
| CUSTOM | &quot;custom&quot; |
| PRODUCT_LISTING | &quot;product_listing&quot; |



