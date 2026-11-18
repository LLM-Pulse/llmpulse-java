

# AiModelDeclinedAnswersResponseSummary


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**answers** | **Integer** | Finished runs of the model, declined ones included |  [optional] |
|**declined** | **Integer** | Answers the model declined |  [optional] |
|**declineRate** | **BigDecimal** |  |  [optional] |
|**safetyFilter** | **Integer** | Answers declined by the model&#39;s own safety filters |  [optional] |
|**safetyFilterRate** | **BigDecimal** |  |  [optional] |
|**topicRefusal** | **Integer** | Answers that declined the topic itself, such as tobacco, gambling or alcohol |  [optional] |
|**topicRefusalRate** | **BigDecimal** |  |  [optional] |
|**lastDeclinedAt** | **OffsetDateTime** | When the latest declined answer of the window was created; null when none was declined |  [optional] |



