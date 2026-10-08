

# GeoAuditUpdateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**cadence** | [**CadenceEnum**](#CadenceEnum) |  |  [optional] |
|**scheduleDay** | **Integer** | Weekly: 0 (Sunday) to 6. Monthly: 1 to 28. |  [optional] |
|**scheduleHour** | **Integer** | Hour of the day, 0 to 23, in the audit time zone |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) | paused stops scheduled runs, active resumes them, archived is the same as DELETE |  [optional] |
|**emailAlerts** | **Boolean** |  |  [optional] |



## Enum: CadenceEnum

| Name | Value |
|---- | -----|
| ONCE | &quot;once&quot; |
| WEEKLY | &quot;weekly&quot; |
| MONTHLY | &quot;monthly&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| PAUSED | &quot;paused&quot; |
| ARCHIVED | &quot;archived&quot; |



