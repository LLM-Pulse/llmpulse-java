

# GeoAuditRunResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**sequence** | **Integer** | Run number within the audit, starting at 1 |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**trigger** | [**TriggerEnum**](#TriggerEnum) |  |  [optional] |
|**score** | **BigDecimal** |  |  [optional] |
|**grade** | **String** |  |  [optional] |
|**scoreDelta** | **BigDecimal** | Score change against the previous completed run |  [optional] |
|**comparableToPrevious** | **Boolean** | False when the checks or the audit settings changed since the previous run, so a diff may reflect that change |  [optional] |
|**newIssues** | **Integer** |  |  [optional] |
|**fixedIssues** | **Integer** |  |  [optional] |
|**regressedIssues** | **Integer** |  |  [optional] |
|**error** | **String** |  |  [optional] |
|**engineVersion** | **String** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**finishedAt** | **OffsetDateTime** |  |  [optional] |
|**appUrl** | **String** |  |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| QUEUED | &quot;queued&quot; |
| RUNNING | &quot;running&quot; |
| COMPLETED | &quot;completed&quot; |
| FAILED | &quot;failed&quot; |
| UNREACHABLE | &quot;unreachable&quot; |



## Enum: TriggerEnum

| Name | Value |
|---- | -----|
| SCHEDULED | &quot;scheduled&quot; |
| MANUAL | &quot;manual&quot; |
| API | &quot;api&quot; |
| MCP | &quot;mcp&quot; |
| LEGACY_IMPORT | &quot;legacy_import&quot; |



