

# AnswerDetails


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**promptId** | **Integer** |  |  [optional] |
|**promptText** | **String** |  |  [optional] |
|**model** | **String** |  |  [optional] |
|**response** | **String** | The AI answer. For a declined answer (no_result_reason declined) it is the reply the model gave instead; for no_answer it is a placeholder, not an AI response |  [optional] |
|**responseTruncated** | **Boolean** |  |  [optional] |
|**executedAt** | **OffsetDateTime** |  |  [optional] |
|**durationMs** | **BigDecimal** | Milliseconds, rounded to one decimal place |  [optional] |
|**success** | **Boolean** | Null while the answer is still pending |  [optional] |
|**noResult** | **Boolean** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics |  [optional] |
|**noResultReason** | [**NoResultReasonEnum**](#NoResultReasonEnum) | Present only when no_result is true. declined &#x3D; the model declined to answer (today only Gemini, shown as Declined in the app) and response holds its reply; no_answer &#x3D; no answer could be collected |  [optional] |
|**fanOutQueries** | **List&lt;String&gt;** |  |  [optional] |
|**mentions** | **List&lt;Object&gt;** |  |  [optional] |
|**citations** | **List&lt;Object&gt;** |  |  [optional] |
|**competitorMentions** | **List&lt;Object&gt;** |  |  [optional] |
|**competitorCitations** | **List&lt;Object&gt;** |  |  [optional] |
|**sentiments** | **List&lt;Object&gt;** | Needs the Growth plan or above; left out below it and named in plan_required_fields |  [optional] |
|**sources** | **List&lt;Object&gt;** |  |  [optional] |
|**shoppingProducts** | **List&lt;Object&gt;** | Needs the Scale plan or above; left out below it and named in plan_required_fields |  [optional] |
|**brandEntities** | **List&lt;Object&gt;** |  |  [optional] |
|**localBusinesses** | **List&lt;Object&gt;** |  |  [optional] |
|**locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  |  [optional] |
|**planRequiredFields** | **List&lt;String&gt;** | The fields left out of this answer because the account&#39;s plan does not include them (sentiments below Growth, shopping_products below Scale). Always present, empty when nothing is left out |  |
|**appUrl** | **URI** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  [optional] |
|**requestId** | **String** |  |  [optional] |



## Enum: NoResultReasonEnum

| Name | Value |
|---- | -----|
| DECLINED | &quot;declined&quot; |
| NO_ANSWER | &quot;no_answer&quot; |



