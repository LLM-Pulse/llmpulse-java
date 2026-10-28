

# CreateApiKey201Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**name** | **String** |  |  |
|**prefix** | **String** | The visible start of the token, to recognize the key. Never the secret itself. |  |
|**scope** | [**ScopeEnum**](#ScopeEnum) |  |  |
|**projectScoped** | **Boolean** | True when the key is limited to project_ids; false for an account-wide key. |  |
|**projectIds** | **List&lt;Integer&gt;** | The projects the key is limited to; empty for an account-wide key. |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**lastUsedAt** | **OffsetDateTime** | Updated at most once a minute. |  |
|**revokedAt** | **OffsetDateTime** |  |  |
|**token** | **String** | The secret to send as Bearer token. Shown only in this response. |  |
|**requestId** | **String** |  |  [optional] |



## Enum: ScopeEnum

| Name | Value |
|---- | -----|
| READ | &quot;read&quot; |
| READ_WRITE | &quot;read_write&quot; |



