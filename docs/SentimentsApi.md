# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getSentimentTags**](SentimentsApi.md#getSentimentTags) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**getSentimentTagsWithHttpInfo**](SentimentsApi.md#getSentimentTagsWithHttpInfo) | **GET** /reports/sentiment/tags | Sentiment by tag (Growth plan or above) |
| [**getSentimentTopics**](SentimentsApi.md#getSentimentTopics) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**getSentimentTopicsWithHttpInfo**](SentimentsApi.md#getSentimentTopicsWithHttpInfo) | **GET** /reports/sentiment/topics | Sentiment by topic (Growth plan or above) |
| [**listSentimentCategories**](SentimentsApi.md#listSentimentCategories) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**listSentimentCategoriesWithHttpInfo**](SentimentsApi.md#listSentimentCategoriesWithHttpInfo) | **GET** /dimensions/sentiments | List sentiment categories (Growth plan or above) |
| [**listSentimentRecords**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records (Growth plan or above) |
| [**listSentimentRecordsWithHttpInfo**](SentimentsApi.md#listSentimentRecordsWithHttpInfo) | **GET** /sentiments | List sentiment records (Growth plan or above) |



## getSentimentTags

> SentimentTagsResponse getSentimentTags(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String topic = "topic_example"; // String | Only sentiments tagged with this topic (case-insensitive)
        String query = "query_example"; // String | Only sentiments whose answer or prompt text contains this text
        String brand = "brand_example"; // String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
        String sort = "mentions"; // String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
        String sortDir = "desc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            SentimentTagsResponse result = apiInstance.getSentimentTags(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#getSentimentTags");
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
| **range** | **Integer**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] [enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: desc, asc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**SentimentTagsResponse**](SentimentTagsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tag rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

## getSentimentTagsWithHttpInfo

> ApiResponse<SentimentTagsResponse> getSentimentTagsWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by tag (Growth plan or above)

One row per tag of the project with at least one analyzed mention, with the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score. A mention counts once for every tag its prompt carries, as on the Sentiment page. Same filters as GET /reports/sentiment/topics. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String topic = "topic_example"; // String | Only sentiments tagged with this topic (case-insensitive)
        String query = "query_example"; // String | Only sentiments whose answer or prompt text contains this text
        String brand = "brand_example"; // String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
        String sort = "mentions"; // String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
        String sortDir = "desc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<SentimentTagsResponse> response = apiInstance.getSentimentTagsWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#getSentimentTags");
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
| **range** | **Integer**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] [enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: desc, asc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**SentimentTagsResponse**](SentimentTagsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tag rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |


## getSentimentTopics

> SentimentTopicsResponse getSentimentTopics(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, &#x60;brand&#x60; empty counts your own brand, &#x60;all&#x60; every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String topic = "topic_example"; // String | Only sentiments tagged with this topic (case-insensitive)
        String query = "query_example"; // String | Only sentiments whose answer or prompt text contains this text
        String brand = "brand_example"; // String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
        String sort = "mentions"; // String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
        String sortDir = "desc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            SentimentTopicsResponse result = apiInstance.getSentimentTopics(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#getSentimentTopics");
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
| **range** | **Integer**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] [enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: desc, asc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**SentimentTopicsResponse**](SentimentTopicsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated topic rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

## getSentimentTopicsWithHttpInfo

> ApiResponse<SentimentTopicsResponse> getSentimentTopicsWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output)

Sentiment by topic (Growth plan or above)

One row per topic AI answers associate with the brand (topics are matched case-insensitively), with its analyzed mentions, the positive (very positive included), neutral and negative counts, their shares on a 0-100 scale and the net sentiment score ((positive - negative) / mentions x 100). The same rows and filters as the Topics tab of the Sentiment page: the window defaults to the last 28 days, &#x60;brand&#x60; empty counts your own brand, &#x60;all&#x60; every brand and a competitor id that competitor. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String topic = "topic_example"; // String | Only sentiments tagged with this topic (case-insensitive)
        String query = "query_example"; // String | Only sentiments whose answer or prompt text contains this text
        String brand = "brand_example"; // String | Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM).
        String sort = "mentions"; // String | Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name.
        String sortDir = "desc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<SentimentTopicsResponse> response = apiInstance.getSentimentTopicsWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, brandKind, analysis, topic, query, brand, sort, sortDir, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#getSentimentTopics");
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
| **range** | **Integer**| Number of days to look back, today included (default 28, like the Sentiment page). Ignored when from or to is given. | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **topic** | **String**| Only sentiments tagged with this topic (case-insensitive) | [optional] |
| **query** | **String**| Only sentiments whose answer or prompt text contains this text | [optional] |
| **brand** | **String**| Whose sentiment to count. Empty or omitted for your own brand, all for every brand, or a competitor id (an unknown id returns ERR_INVALID_PARAM). | [optional] |
| **sort** | **String**| Sort column: mentions, name (the topic or tag), positive, negative or neutral (their shares) or net_score. Ties sort by name. | [optional] [default to mentions] [enum: mentions, name, positive, negative, neutral, net_score] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: desc, asc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**SentimentTopicsResponse**](SentimentTopicsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated topic rows |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |


## listSentimentCategories

> void listSentimentCategories(projectId, output)

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listSentimentCategories(projectId, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#listSentimentCategories");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Sentiment buckets |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |

## listSentimentCategoriesWithHttpInfo

> ApiResponse<Void> listSentimentCategoriesWithHttpInfo(projectId, output)

List sentiment categories (Growth plan or above)

Sentiment metric keys + labels + colors. For records, use /sentiments. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listSentimentCategoriesWithHttpInfo(projectId, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#listSentimentCategories");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Sentiment buckets |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |


## listSentimentRecords

> SentimentsResponse listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer competitorId = 56; // Integer | 
        Boolean brandOnly = true; // Boolean | 
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String model = "chatgpt"; // String | Filter by one AI model. Here an unknown value, or a model the API key's user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            SentimentsResponse result = apiInstance.listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#listSentimentRecords");
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
| **competitorId** | **Integer**|  | [optional] |
| **brandOnly** | **Boolean**|  | [optional] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **model** | **String**| Filter by one AI model. Here an unknown value, or a model the API key&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**SentimentsResponse**](SentimentsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sentiments |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

## listSentimentRecordsWithHttpInfo

> ApiResponse<SentimentsResponse> listSentimentRecordsWithHttpInfo(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records (Growth plan or above)

Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SentimentsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SentimentsApi apiInstance = new SentimentsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer competitorId = 56; // Integer | 
        Boolean brandOnly = true; // Boolean | 
        String analysis = "analysis_example"; // String | One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative
        String model = "chatgpt"; // String | Filter by one AI model. Here an unknown value, or a model the API key's user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<SentimentsResponse> response = apiInstance.listSentimentRecordsWithHttpInfo(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SentimentsApi#listSentimentRecords");
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
| **competitorId** | **Integer**|  | [optional] |
| **brandOnly** | **Boolean**|  | [optional] |
| **analysis** | **String**| One sentiment level or a comma-separated list: very_positive, positive, neutral, negative, very_negative | [optional] |
| **model** | **String**| Filter by one AI model. Here an unknown value, or a model the API key&#39;s user has not enabled, is ignored rather than rejected: the request succeeds and returns the records of every enabled model, as if model were omitted. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**SentimentsResponse**](SentimentsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated sentiments |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

