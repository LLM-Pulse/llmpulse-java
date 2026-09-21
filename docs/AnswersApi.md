# AnswersApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAnswer**](AnswersApi.md#getAnswer) | **GET** /answers/{id} | Get one AI response |
| [**getAnswerWithHttpInfo**](AnswersApi.md#getAnswerWithHttpInfo) | **GET** /answers/{id} | Get one AI response |
| [**listAnswers**](AnswersApi.md#listAnswers) | **GET** /answers | List AI responses |
| [**listAnswersWithHttpInfo**](AnswersApi.md#listAnswersWithHttpInfo) | **GET** /answers | List AI responses |



## getAnswer

> AnswerDetails getAnswer(projectId, id, includeSourcePageDetails)

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass &#x60;include_source_page_details&#x3D;true&#x60; to nest page-cache metadata under each source.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AnswersApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AnswersApi apiInstance = new AnswersApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        Boolean includeSourcePageDetails = false; // Boolean | 
        try {
            AnswerDetails result = apiInstance.getAnswer(projectId, id, includeSourcePageDetails);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AnswersApi#getAnswer");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **projectId** | **Integer**| Project ID | |
| **id** | **Integer**|  | |
| **includeSourcePageDetails** | **Boolean**|  | [optional] [default to false] |

### Return type

[**AnswerDetails**](AnswerDetails.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Answer details |  -  |
| **404** | Resource not found |  -  |

## getAnswerWithHttpInfo

> ApiResponse<AnswerDetails> getAnswerWithHttpInfo(projectId, id, includeSourcePageDetails)

Get one AI response

Full answer with mentions, citations, sentiments, sources, shopping_products, brand_entities, fan_out_queries. Pass &#x60;include_source_page_details&#x3D;true&#x60; to nest page-cache metadata under each source.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AnswersApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AnswersApi apiInstance = new AnswersApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        Boolean includeSourcePageDetails = false; // Boolean | 
        try {
            ApiResponse<AnswerDetails> response = apiInstance.getAnswerWithHttpInfo(projectId, id, includeSourcePageDetails);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AnswersApi#getAnswer");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **projectId** | **Integer**| Project ID | |
| **id** | **Integer**|  | |
| **includeSourcePageDetails** | **Boolean**|  | [optional] [default to false] |

### Return type

ApiResponse<[**AnswerDetails**](AnswerDetails.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Answer details |  -  |
| **404** | Resource not found |  -  |


## listAnswers

> void listAnswers(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query, noResult)

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass &#x60;query&#x60; for case-insensitive full-text search inside response texts: &#x60;total&#x60; becomes the exact count of matching responses and each item returns &#x60;snippet&#x60; + &#x60;match_count&#x60; instead of &#x60;response&#x60;/&#x60;response_truncated&#x60;.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AnswersApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AnswersApi apiInstance = new AnswersApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String mentionFilter = "mentions_you"; // String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
        String citationFilter = "cites_you"; // String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String query = "query_example"; // String | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode.
        Boolean noResult = true; // Boolean | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false = only real answers, true = only sentinels, omit = both. Every item carries its own no_result flag.
        try {
            apiInstance.listAnswers(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query, noResult);
        } catch (ApiException e) {
            System.err.println("Exception when calling AnswersApi#listAnswers");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Reason: " + e.getResponseBody());
            System.err.println("Response headers: " + e.getResponseHeaders());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **projectId** | **Integer**| Project ID | |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **mentionFilter** | **String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | **String**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] [enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **query** | **String**| Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [optional] |
| **noResult** | **Boolean**| Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false &#x3D; only real answers, true &#x3D; only sentinels, omit &#x3D; both. Every item carries its own no_result flag. | [optional] |

### Return type


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated answers |  -  |
| **422** | Invalid parameters |  -  |

## listAnswersWithHttpInfo

> ApiResponse<Void> listAnswersWithHttpInfo(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query, noResult)

List AI responses

Successful prompt-execution responses with truncated content (max 10,000 chars). Pass &#x60;query&#x60; for case-insensitive full-text search inside response texts: &#x60;total&#x60; becomes the exact count of matching responses and each item returns &#x60;snippet&#x60; + &#x60;match_count&#x60; instead of &#x60;response&#x60;/&#x60;response_truncated&#x60;.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AnswersApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AnswersApi apiInstance = new AnswersApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String mentionFilter = "mentions_you"; // String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
        String citationFilter = "cites_you"; // String | Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you).
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String query = "query_example"; // String | Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode.
        Boolean noResult = true; // Boolean | Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false = only real answers, true = only sentinels, omit = both. Every item carries its own no_result flag.
        try {
            ApiResponse<Void> response = apiInstance.listAnswersWithHttpInfo(projectId, model, collectionId, countryCode, languageCode, prompt, mentionFilter, citationFilter, competitors, from, to, page, perPage, query, noResult);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling AnswersApi#listAnswers");
            System.err.println("Status code: " + e.getCode());
            System.err.println("Response headers: " + e.getResponseHeaders());
            System.err.println("Reason: " + e.getResponseBody());
            e.printStackTrace();
        }
    }
}
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **projectId** | **Integer**| Project ID | |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **mentionFilter** | **String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **citationFilter** | **String**| Same two-axis matrix applied to the domains cited in the answer instead of the brands named in it. Independent of mention_filter; pass both to intersect them (e.g. mentions_you + not_cites_you finds answers that talk about you without linking to you). | [optional] [enum: cites_you, not_cites_you, cites_competitor, not_cites_competitor, you_and_competitor, competitor_not_you, you_not_competitor, cites_no_brands] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **query** | **String**| Case-insensitive full-text search inside AI response texts. Switches items to snippet + match_count mode. | [optional] |
| **noResult** | **Boolean**| Filter sentinel non-answers (provider returned nothing after retries; excluded from platform metrics). false &#x3D; only real answers, true &#x3D; only sentinels, omit &#x3D; both. Every item carries its own no_result flag. | [optional] |

### Return type


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated answers |  -  |
| **422** | Invalid parameters |  -  |

