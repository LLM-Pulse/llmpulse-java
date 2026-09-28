

# Competitor


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**name** | **String** |  |  [optional] |
|**domain** | **String** | Bare (scheme-less) domain. Null only on the own-brand row (include_project_brand&#x3D;true) when the project has no URL. |  [optional] |
|**actorType** | [**ActorTypeEnum**](#ActorTypeEnum) | Only present when include_project_brand&#x3D;true |  [optional] |
|**isOwn** | **Boolean** | Only present when include_project_brand&#x3D;true |  [optional] |



## Enum: ActorTypeEnum

| Name | Value |
|---- | -----|
| PROJECT | &quot;project&quot; |
| COMPETITOR | &quot;competitor&quot; |



