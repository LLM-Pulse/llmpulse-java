# AiModelInsightsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAiModelInsightsSummary**](AiModelInsightsApi.md#getAiModelInsightsSummary) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary |
| [**getAiModelInsightsSummaryWithHttpInfo**](AiModelInsightsApi.md#getAiModelInsightsSummaryWithHttpInfo) | **GET** /reports/ai_model_insights/summary | AI Model Insights summary |
| [**getAiModelPositionDistribution**](AiModelInsightsApi.md#getAiModelPositionDistribution) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison |
| [**getAiModelPositionDistributionWithHttpInfo**](AiModelInsightsApi.md#getAiModelPositionDistributionWithHttpInfo) | **GET** /reports/ai_model_insights/position_distribution | Position distribution comparison |
| [**getAiOverviewResults**](AiModelInsightsApi.md#getAiOverviewResults) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability |
| [**getAiOverviewResultsWithHttpInfo**](AiModelInsightsApi.md#getAiOverviewResultsWithHttpInfo) | **GET** /reports/ai_model_insights/ai_overview_results | Google AI Overview result availability |



## getAiModelInsightsSummary

> void getAiModelInsightsSummary(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors)

AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape &#x60;{ type, id, competitor_id, name, domain }&#x60; with bare (scheme-less) domains.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        try {
            apiInstance.getAiModelInsightsSummary(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiModelInsightsSummary");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |

### Return type


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary |  -  |

## getAiModelInsightsSummaryWithHttpInfo

> ApiResponse<Void> getAiModelInsightsSummaryWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors)

AI Model Insights summary

Per-model mentions, citations, brand net sentiment with raw counts, weighted visibility totals/shares, plus actor matrices. All actor entries use the standard shape &#x60;{ type, id, competitor_id, name, domain }&#x60; with bare (scheme-less) domains.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        try {
            ApiResponse<Void> response = apiInstance.getAiModelInsightsSummaryWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, competitors);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiModelInsightsSummary");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |

### Return type


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary |  -  |


## getAiModelPositionDistribution

> void getAiModelPositionDistribution(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2)

Position distribution comparison

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer brand1 = 56; // Integer | Competitor ID for the first comparison brand (omit to compare project brand)
        Integer brand2 = 56; // Integer | 
        try {
            apiInstance.getAiModelPositionDistribution(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiModelPositionDistribution");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **brand1** | **Integer**| Competitor ID for the first comparison brand (omit to compare project brand) | [optional] |
| **brand2** | **Integer**|  | [optional] |

### Return type


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bucketed position totals + chart-ready series |  -  |

## getAiModelPositionDistributionWithHttpInfo

> ApiResponse<Void> getAiModelPositionDistributionWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2)

Position distribution comparison

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer brand1 = 56; // Integer | Competitor ID for the first comparison brand (omit to compare project brand)
        Integer brand2 = 56; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.getAiModelPositionDistributionWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, model, brand1, brand2);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiModelPositionDistribution");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **brand1** | **Integer**| Competitor ID for the first comparison brand (omit to compare project brand) | [optional] |
| **brand2** | **Integer**|  | [optional] |

### Return type


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bucketed position totals + chart-ready series |  -  |


## getAiOverviewResults

> void getAiOverviewResults(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage)

Google AI Overview result availability

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.getAiOverviewResults(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiOverviewResults");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI Overview result-availability data + per-prompt table |  -  |

## getAiOverviewResultsWithHttpInfo

> ApiResponse<Void> getAiOverviewResultsWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage)

Google AI Overview result availability

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiModelInsightsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiModelInsightsApi apiInstance = new AiModelInsightsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.getAiOverviewResultsWithHttpInfo(projectId, range, from, to, granularity, collectionId, countryCode, languageCode, promptType, brandKind, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiModelInsightsApi#getAiOverviewResults");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | AI Overview result-availability data + per-prompt table |  -  |

