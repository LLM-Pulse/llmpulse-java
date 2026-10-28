

# CreateApiKeyRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**name** | **String** | A label to recognize the key, for example the customer it is for |  |
|**scope** | [**ScopeEnum**](#ScopeEnum) | read (default) only reads data; read_write can also create, change and delete within the key&#39;s projects |  [optional] |
|**projectIds** | **List&lt;Integer&gt;** | The projects the key is limited to, at least one |  |



## Enum: ScopeEnum

| Name | Value |
|---- | -----|
| READ | &quot;read&quot; |
| READ_WRITE | &quot;read_write&quot; |



