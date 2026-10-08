

# GeoAuditCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**target** | **String** | The domain (site-wide types) or page URL to audit |  |
|**auditTypes** | [**List&lt;AuditTypesEnum&gt;**](#List&lt;AuditTypesEnum&gt;) | One or more audit types; each becomes its own audit and starts its first run |  |
|**cadence** | [**CadenceEnum**](#CadenceEnum) | once (default), weekly or monthly. Weekly and monthly need a type whose checks are tracked and count against the plan limit of recurring audits |  [optional] |



## Enum: List&lt;AuditTypesEnum&gt;

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



