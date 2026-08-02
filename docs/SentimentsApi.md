# SentimentsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listSentimentRecords**](SentimentsApi.md#listSentimentRecords) | **GET** /sentiments | List sentiment records |
| [**listSentimentRecordsWithHttpInfo**](SentimentsApi.md#listSentimentRecordsWithHttpInfo) | **GET** /sentiments | List sentiment records |



## listSentimentRecords

> void listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records

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
        String analysis = "very_positive"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.listSentimentRecords(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage);
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
| **analysis** | **String**|  | [optional] [enum: very_positive, positive, neutral, negative, very_negative] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

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
| **200** | Paginated sentiments |  -  |
| **422** | Invalid parameters |  -  |

## listSentimentRecordsWithHttpInfo

> ApiResponse<Void> listSentimentRecordsWithHttpInfo(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage)

List sentiment records

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
        String analysis = "very_positive"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.listSentimentRecordsWithHttpInfo(projectId, competitorId, brandOnly, analysis, model, collectionId, countryCode, languageCode, from, to, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
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
| **analysis** | **String**|  | [optional] [enum: very_positive, positive, neutral, negative, very_negative] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

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
| **200** | Paginated sentiments |  -  |
| **422** | Invalid parameters |  -  |

