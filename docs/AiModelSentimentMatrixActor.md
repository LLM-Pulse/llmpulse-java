

# AiModelSentimentMatrixActor

An actor (the standard actor shape) with one net sentiment cell per model

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**type** | [**TypeEnum**](#TypeEnum) |  |  [optional] |
|**id** | **Integer** | Project id, or competitor id |  [optional] |
|**competitorId** | **Integer** | Null for the project, the competitor id otherwise |  [optional] |
|**name** | **String** |  |  [optional] |
|**domain** | **String** | Bare (scheme-less) domain. Null for the project actor when the project has no URL. |  [optional] |
|**totalSentiments** | **Integer** | The actor&#39;s sentiment verdicts summed over the models |  [optional] |
|**models** | [**Map&lt;String, AiModelSentimentCell&gt;**](AiModelSentimentCell.md) | One cell per model, keyed by model |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| PROJECT | &quot;project&quot; |
| COMPETITOR | &quot;competitor&quot; |



