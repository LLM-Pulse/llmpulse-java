

# AnswerDetails


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**promptId** | **Integer** |  |  [optional] |
|**promptText** | **String** |  |  [optional] |
|**model** | **String** |  |  [optional] |
|**response** | **String** |  |  [optional] |
|**responseTruncated** | **Boolean** |  |  [optional] |
|**executedAt** | **OffsetDateTime** |  |  [optional] |
|**durationMs** | **BigDecimal** | Milliseconds, rounded to one decimal place |  [optional] |
|**success** | **Boolean** | Null while the answer is still pending |  [optional] |
|**noResult** | **Boolean** | True for a sentinel non-answer (the provider returned nothing after retries); excluded from platform metrics |  [optional] |
|**fanOutQueries** | **List&lt;String&gt;** |  |  [optional] |
|**mentions** | **List&lt;Object&gt;** |  |  [optional] |
|**citations** | **List&lt;Object&gt;** |  |  [optional] |
|**competitorMentions** | **List&lt;Object&gt;** |  |  [optional] |
|**competitorCitations** | **List&lt;Object&gt;** |  |  [optional] |
|**sentiments** | **List&lt;Object&gt;** |  |  [optional] |
|**sources** | **List&lt;Object&gt;** |  |  [optional] |
|**shoppingProducts** | **List&lt;Object&gt;** |  |  [optional] |
|**brandEntities** | **List&lt;Object&gt;** |  |  [optional] |
|**localBusinesses** | **List&lt;Object&gt;** |  |  [optional] |
|**locale** | [**AnswerDetailsLocale**](AnswerDetailsLocale.md) |  |  [optional] |
|**appUrl** | **URI** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  [optional] |
|**requestId** | **String** |  |  [optional] |



