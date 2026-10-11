

# IntelligenceTaskSummary


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**publicId** | **String** |  |  |
|**taskType** | **String** |  |  |
|**title** | **String** |  |  |
|**status** | **String** |  |  |
|**promptId** | **Integer** |  |  |
|**promptText** | **String** |  |  |
|**wordCount** | **Integer** |  |  |
|**manuallyEditedAt** | **OffsetDateTime** | When the content was last edited by hand; null while the output is as generated |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**processedAt** | **OffsetDateTime** |  |  |
|**resultVersion** | **String** | Concurrency token for content edits: send it back as result_version on PATCH /intelligence_tasks/{id} so an edit composed before a regeneration is refused with ERR_STALE_CONTENT (409). It is \&quot;0\&quot; until the task first completes, then changes each time a generation or regeneration replaces result_data, never on a manual edit or a revert. Treat it as opaque text |  |



