# CitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getCitedUrlContent**](CitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlContentWithHttpInfo**](CitationIntelligenceApi.md#getCitedUrlContentWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail**](CitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getCitedUrlDetailWithHttpInfo**](CitationIntelligenceApi.md#getCitedUrlDetailWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain**](CitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**getMentionsByCitingDomainWithHttpInfo**](CitationIntelligenceApi.md#getMentionsByCitingDomainWithHttpInfo) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**listCitationGroups**](CitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitationGroupsWithHttpInfo**](CitationIntelligenceApi.md#listCitationGroupsWithHttpInfo) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences**](CitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**listCitedUrlOccurrencesWithHttpInfo**](CitationIntelligenceApi.md#listCitedUrlOccurrencesWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |



## getCitedUrlContent

> void getCitedUrlContent(projectId, urlSha256)

Cited URL cached content

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            apiInstance.getCitedUrlContent(projectId, urlSha256);
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getCitedUrlContent");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |

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
| **200** | Sanitized cached content + mention evidence |  -  |
| **404** | Resource not found |  -  |

## getCitedUrlContentWithHttpInfo

> ApiResponse<Void> getCitedUrlContentWithHttpInfo(projectId, urlSha256)

Cited URL cached content

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            ApiResponse<Void> response = apiInstance.getCitedUrlContentWithHttpInfo(projectId, urlSha256);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getCitedUrlContent");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |

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
| **200** | Sanitized cached content + mention evidence |  -  |
| **404** | Resource not found |  -  |


## getCitedUrlDetail

> void getCitedUrlDetail(projectId, urlSha256)

Cited URL detail

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            apiInstance.getCitedUrlDetail(projectId, urlSha256);
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getCitedUrlDetail");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |

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
| **200** | URL-level intelligence |  -  |
| **404** | Resource not found |  -  |

## getCitedUrlDetailWithHttpInfo

> ApiResponse<Void> getCitedUrlDetailWithHttpInfo(projectId, urlSha256)

Cited URL detail

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            ApiResponse<Void> response = apiInstance.getCitedUrlDetailWithHttpInfo(projectId, urlSha256);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getCitedUrlDetail");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |

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
| **200** | URL-level intelligence |  -  |
| **404** | Resource not found |  -  |


## getMentionsByCitingDomain

> void getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        List<String> domains = Arrays.asList(); // List<String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        try {
            apiInstance.getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to);
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getMentionsByCitingDomain");
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
| **domains** | [**List&lt;String&gt;**](String.md)| Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |

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
| **200** | Mention share per citing domain |  -  |
| **422** | Invalid parameters |  -  |

## getMentionsByCitingDomainWithHttpInfo

> ApiResponse<Void> getMentionsByCitingDomainWithHttpInfo(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to)

Mention share by citing domain

For the responses where each given source domain is cited, returns the share of those responses that mention the brand vs each competitor (brand + competitors sum to 100% per domain). Pass multiple domains to get the whole matrix in one call.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        List<String> domains = Arrays.asList(); // List<String> | Source domains to analyze, e.g. domains[]=gmac.com&domains[]=educaweb.com
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        try {
            ApiResponse<Void> response = apiInstance.getMentionsByCitingDomainWithHttpInfo(projectId, domains, model, collectionId, countryCode, languageCode, prompt, from, to);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#getMentionsByCitingDomain");
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
| **domains** | [**List&lt;String&gt;**](String.md)| Source domains to analyze, e.g. domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com | |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |

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
| **200** | Mention share per citing domain |  -  |
| **422** | Invalid parameters |  -  |


## listCitationGroups

> void listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String view = "url"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String order = "group_key"; // String | 
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String query = "query_example"; // String | 
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | 
        try {
            apiInstance.listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap);
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#listCitationGroups");
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
| **view** | **String**|  | [optional] [default to url] [enum: url, domain, host] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **order** | **String**|  | [optional] [enum: group_key, total_responses, total_citations, citation_rate, avg_citation_position, first_seen_at, last_seen_at] |
| **direction** | **String**|  | [optional] [enum: asc, desc] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **query** | **String**|  | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**|  | [optional] [enum: mentioned, gap] |

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
| **200** | Grouped citation intelligence |  -  |
| **422** | Invalid parameters |  -  |

## listCitationGroupsWithHttpInfo

> ApiResponse<Void> listCitationGroupsWithHttpInfo(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String view = "url"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String order = "group_key"; // String | 
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String query = "query_example"; // String | 
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | 
        try {
            ApiResponse<Void> response = apiInstance.listCitationGroupsWithHttpInfo(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, from, to, query, sourceType, sentiment, contentGap);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#listCitationGroups");
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
| **view** | **String**|  | [optional] [default to url] [enum: url, domain, host] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **order** | **String**|  | [optional] [enum: group_key, total_responses, total_citations, citation_rate, avg_citation_position, first_seen_at, last_seen_at] |
| **direction** | **String**|  | [optional] [enum: asc, desc] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **query** | **String**|  | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**|  | [optional] [enum: mentioned, gap] |

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
| **200** | Grouped citation intelligence |  -  |
| **422** | Invalid parameters |  -  |


## listCitedUrlOccurrences

> void listCitedUrlOccurrences(projectId, urlSha256, page, perPage)

Cited URL occurrences

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.listCitedUrlOccurrences(projectId, urlSha256, page, perPage);
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#listCitedUrlOccurrences");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |
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
| **200** | Paginated occurrences |  -  |
| **404** | Resource not found |  -  |

## listCitedUrlOccurrencesWithHttpInfo

> ApiResponse<Void> listCitedUrlOccurrencesWithHttpInfo(projectId, urlSha256, page, perPage)

Cited URL occurrences

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CitationIntelligenceApi apiInstance = new CitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.listCitedUrlOccurrencesWithHttpInfo(projectId, urlSha256, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CitationIntelligenceApi#listCitedUrlOccurrences");
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
| **urlSha256** | **String**| 64-character hex SHA-256 of the cited URL | |
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
| **200** | Paginated occurrences |  -  |
| **404** | Resource not found |  -  |

