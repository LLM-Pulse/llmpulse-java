

# GeoAuditComparisonChangesInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**checkKey** | **String** |  |  [optional] |
|**checkTitle** | **String** |  |  [optional] |
|**subjectKey** | **String** |  |  [optional] |
|**subject** | **String** |  |  [optional] |
|**severity** | **String** |  |  [optional] |
|**fromStatus** | **String** |  |  [optional] |
|**toStatus** | **String** |  |  [optional] |
|**change** | [**ChangeEnum**](#ChangeEnum) |  |  [optional] |



## Enum: ChangeEnum

| Name | Value |
|---- | -----|
| NEW | &quot;new&quot; |
| FIXED | &quot;fixed&quot; |
| CHANGED | &quot;changed&quot; |
| APPEARED | &quot;appeared&quot; |
| DISAPPEARED | &quot;disappeared&quot; |
| UNCHANGED | &quot;unchanged&quot; |



