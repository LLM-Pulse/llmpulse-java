

# GeoAuditIssueResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**checkKey** | **String** |  |  [optional] |
|**checkTitle** | **String** |  |  [optional] |
|**subjectKey** | **String** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**severity** | **String** |  |  [optional] |
|**state** | [**StateEnum**](#StateEnum) |  |  [optional] |
|**badge** | [**BadgeEnum**](#BadgeEnum) | How the latest comparable run moved the issue |  [optional] |
|**accepted** | **Boolean** |  |  [optional] |
|**acceptedAt** | **OffsetDateTime** |  |  [optional] |
|**regressionCount** | **Integer** |  |  [optional] |
|**evidence** | **Object** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: StateEnum

| Name | Value |
|---- | -----|
| OPEN | &quot;open&quot; |
| FIXED | &quot;fixed&quot; |
| GONE | &quot;gone&quot; |



## Enum: BadgeEnum

| Name | Value |
|---- | -----|
| NEW | &quot;new&quot; |
| PERSISTING | &quot;persisting&quot; |
| REGRESSED | &quot;regressed&quot; |
| FIXED | &quot;fixed&quot; |
| GONE | &quot;gone&quot; |



