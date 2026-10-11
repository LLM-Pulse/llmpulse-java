

# TeamMember


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**email** | **String** |  |  |
|**name** | **String** |  |  [optional] |
|**role** | [**RoleEnum**](#RoleEnum) | The account owner is listed first; everyone else who joined is a member. |  |
|**status** | [**StatusEnum**](#StatusEnum) | A blocked member cannot sign in or use the API until unblocked in the app. |  |
|**permissionRole** | **String** | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. |  |
|**accountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  |  |
|**permissions** | **Map&lt;String, List&lt;String&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. |  |
|**accountAdmin** | **Boolean** | A co-owner, who can manage the team. |  |
|**billingAccess** | **Boolean** | Can open Billing and Plans (always true for the owner). |  |
|**allProjects** | **Boolean** | Has access to every project of the account, including future ones. |  |
|**projectIds** | **List&lt;Integer&gt;** | The projects a member is limited to; empty when all_projects is true. |  |
|**lastSignInAt** | **OffsetDateTime** |  |  [optional] |
|**joinedAt** | **OffsetDateTime** | When the member accepted the invitation; null for the owner and for members added without one. |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |



## Enum: RoleEnum

| Name | Value |
|---- | -----|
| OWNER | &quot;owner&quot; |
| MEMBER | &quot;member&quot; |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| ACTIVE | &quot;active&quot; |
| BLOCKED | &quot;blocked&quot; |



