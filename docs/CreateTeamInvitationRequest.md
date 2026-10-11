

# CreateTeamInvitationRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**email** | **String** |  |  |
|**projectIds** | **List&lt;Integer&gt;** | Projects the member can access. Send this or all_projects true. |  [optional] |
|**allProjects** | **Boolean** | Access to every project, including future ones |  [optional] |
|**permissionRole** | [**PermissionRoleEnum**](#PermissionRoleEnum) | Default full_access. Owner and co-owners only. |  [optional] |
|**accountRoleId** | **Integer** | One of the account&#39;s roles, with permission_role account_role |  [optional] |
|**permissions** | **Map&lt;String, List&lt;String&gt;&gt;** | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\&quot;overview\&quot;: [\&quot;read\&quot;], \&quot;prompts\&quot;: [\&quot;read\&quot;, \&quot;create\&quot;]} |  [optional] |
|**accountAdmin** | **Boolean** | Make the member a co-owner. Account owner only. |  [optional] |
|**billingAccess** | **Boolean** | Access to Billing and Plans. Account owner only. |  [optional] |



## Enum: PermissionRoleEnum

| Name | Value |
|---- | -----|
| FULL_ACCESS | &quot;full_access&quot; |
| VIEW_ONLY | &quot;view_only&quot; |
| CUSTOM | &quot;custom&quot; |
| ACCOUNT_ROLE | &quot;account_role&quot; |



