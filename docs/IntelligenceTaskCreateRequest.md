

# IntelligenceTaskCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**taskType** | [**TaskTypeEnum**](#TaskTypeEnum) |  |  |
|**promptId** | **Integer** |  |  [optional] |
|**customTopic** | **String** |  |  [optional] |
|**userInstructions** | **String** |  |  [optional] |
|**outputLanguageCode** | **String** |  |  [optional] |
|**existingContent** | **String** |  |  [optional] |
|**existingContentUrl** | **URI** |  |  [optional] |



## Enum: TaskTypeEnum

| Name | Value |
|---- | -----|
| BRIEF | &quot;brief&quot; |
| CREATE | &quot;create&quot; |
| UPDATE | &quot;update&quot; |
| PR_INSIGHTS | &quot;pr_insights&quot; |
| CUSTOM | &quot;custom&quot; |



