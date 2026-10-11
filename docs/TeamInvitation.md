

# TeamInvitation


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** | Kept by the member once they accept, when they move to GET /team_members. |  |
|**email** | **String** |  |  |
|**permissionRole** | [**PermissionRoleEnum**](#PermissionRoleEnum) |  |  |
|**accountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
|**permissions** | **Map&lt;String, List&lt;String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
|**accountAdmin** | **Boolean** |  |  |
|**billingAccess** | **Boolean** |  |  |
|**allProjects** | **Boolean** |  |  |
|**projectIds** | **List&lt;Integer&gt;** |  |  |
|**invitedAt** | **OffsetDateTime** | When the invitation email was last sent. |  [optional] |
|**expiresAt** | **OffsetDateTime** | When the invitation link stops working. |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |



## Enum: PermissionRoleEnum

| Name | Value |
|---- | -----|
| FULL_ACCESS | &quot;full_access&quot; |
| VIEW_ONLY | &quot;view_only&quot; |
| CUSTOM | &quot;custom&quot; |
| ACCOUNT_ROLE | &quot;account_role&quot; |



