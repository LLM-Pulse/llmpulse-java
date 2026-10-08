

# GeoAuditFinding


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**checkKey** | **String** | Stable key of the check within its audit type |  [optional] |
|**checkTitle** | **String** |  |  [optional] |
|**subjectKey** | **String** | What the check is about (site for site-wide checks, a bot slug for robots.txt bot checks) |  [optional] |
|**subject** | **String** |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**severity** | [**SeverityEnum**](#SeverityEnum) |  |  [optional] |
|**evidence** | **Object** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PASS | &quot;pass&quot; |
| WARN | &quot;warn&quot; |
| FAIL | &quot;fail&quot; |
| INFO | &quot;info&quot; |
| NOT_APPLICABLE | &quot;not_applicable&quot; |
| UNKNOWN | &quot;unknown&quot; |



## Enum: SeverityEnum

| Name | Value |
|---- | -----|
| CRITICAL | &quot;critical&quot; |
| HIGH | &quot;high&quot; |
| MEDIUM | &quot;medium&quot; |
| LOW | &quot;low&quot; |
| INFO | &quot;info&quot; |



