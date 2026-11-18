

# AiModelDeclinedAnswersResponseChartInner


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
|**date** | **LocalDate** | First day of the tracking period |  |



