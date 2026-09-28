

# IntelligenceTaskUpdateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**publicId** | **String** |  |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**taskType** | **String** |  |  [optional] |
|**title** | **String** |  |  [optional] |
|**status** | **String** |  |  [optional] |
|**promptId** | **Integer** |  |  [optional] |
|**promptText** | **String** |  |  [optional] |
|**agenticMode** | **Boolean** |  |  [optional] |
|**customTopic** | **String** |  |  [optional] |
|**userInstructions** | **String** |  |  [optional] |
|**outputLanguageCode** | **String** |  |  [optional] |
|**wordCount** | **Integer** |  |  [optional] |
|**resultData** | **Object** | The generated content once status is completed; null before that |  [optional] |
|**errorMessage** | **String** |  |  [optional] |
|**estimatedTime** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**processedAt** | **OffsetDateTime** |  |  [optional] |
|**manuallyEditedAt** | **OffsetDateTime** | When the content was last edited by hand; null while the output is as generated |  [optional] |
|**editedByUserId** | **Integer** | User behind the last manual edit; null for an unedited task or an edit made from an embedded portal |  [optional] |
|**requestId** | **String** |  |  [optional] |
|**changedPaths** | **List&lt;String&gt;** | Paths whose text actually changed; empty when every value matched the stored text |  [optional] |



