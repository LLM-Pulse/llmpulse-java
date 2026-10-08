

# GeoAudit


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **String** | Stable audit id |  [optional] |
|**auditType** | [**AuditTypeEnum**](#AuditTypeEnum) |  |  [optional] |
|**target** | **String** | The audited domain (site-wide types) or page URL, normalized |  [optional] |
|**countryCode** | **String** |  |  [optional] |
|**cadence** | [**CadenceEnum**](#CadenceEnum) |  |  [optional] |
|**status** | [**StatusEnum**](#StatusEnum) |  |  [optional] |
|**pausedReason** | **String** | user, or unreachable when three runs in a row could not reach the site |  [optional] |
|**schedule** | [**GeoAuditSchedule**](GeoAuditSchedule.md) |  |  [optional] |
|**nextRunAt** | **OffsetDateTime** |  |  [optional] |
|**emailAlerts** | **Boolean** |  |  [optional] |
|**recurringAvailable** | **Boolean** | Whether this audit type can run weekly or monthly |  [optional] |
|**checksTracked** | **Boolean** | Whether runs of this type produce findings and issues, or a score only |  [optional] |
|**latestRun** | [**GeoAuditRun**](GeoAuditRun.md) |  |  [optional] |
|**openIssues** | **Integer** |  |  [optional] |
|**openCriticalIssues** | **Integer** |  |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**appUrl** | **String** |  |  [optional] |



## Enum: AuditTypeEnum

| Name | Value |
|---- | -----|
| AGENT_READINESS | &quot;agent_readiness&quot; |
| ROBOTS_TXT | &quot;robots_txt&quot; |
| CRAWLABILITY | &quot;crawlability&quot; |
| SCHEMA | &quot;schema&quot; |
| CONTENT_READINESS | &quot;content_readiness&quot; |
| DISCOVERABILITY | &quot;discoverability&quot; |
| SITE_STRUCTURE | &quot;site_structure&quot; |



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



