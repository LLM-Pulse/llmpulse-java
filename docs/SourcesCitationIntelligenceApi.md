# SourcesCitationIntelligenceApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addUrlListEntries**](SourcesCitationIntelligenceApi.md#addUrlListEntries) | **POST** /url_lists/{id}/entries | Add entries to a URL list |
| [**addUrlListEntriesWithHttpInfo**](SourcesCitationIntelligenceApi.md#addUrlListEntriesWithHttpInfo) | **POST** /url_lists/{id}/entries | Add entries to a URL list |
| [**createUrlList**](SourcesCitationIntelligenceApi.md#createUrlList) | **POST** /url_lists | Create a URL list |
| [**createUrlListWithHttpInfo**](SourcesCitationIntelligenceApi.md#createUrlListWithHttpInfo) | **POST** /url_lists | Create a URL list |
| [**deleteUrlList**](SourcesCitationIntelligenceApi.md#deleteUrlList) | **DELETE** /url_lists/{id} | Delete a URL list |
| [**deleteUrlListWithHttpInfo**](SourcesCitationIntelligenceApi.md#deleteUrlListWithHttpInfo) | **DELETE** /url_lists/{id} | Delete a URL list |
| [**getCitedUrlContent**](SourcesCitationIntelligenceApi.md#getCitedUrlContent) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlContentWithHttpInfo**](SourcesCitationIntelligenceApi.md#getCitedUrlContentWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256}/content | Cited URL cached content |
| [**getCitedUrlDetail**](SourcesCitationIntelligenceApi.md#getCitedUrlDetail) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getCitedUrlDetailWithHttpInfo**](SourcesCitationIntelligenceApi.md#getCitedUrlDetailWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256} | Cited URL detail |
| [**getMentionsByCitingDomain**](SourcesCitationIntelligenceApi.md#getMentionsByCitingDomain) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**getMentionsByCitingDomainWithHttpInfo**](SourcesCitationIntelligenceApi.md#getMentionsByCitingDomainWithHttpInfo) | **GET** /citation_intelligence/mentions_by_domain | Mention share by citing domain |
| [**getUrlList**](SourcesCitationIntelligenceApi.md#getUrlList) | **GET** /url_lists/{id} | Get a URL list report |
| [**getUrlListWithHttpInfo**](SourcesCitationIntelligenceApi.md#getUrlListWithHttpInfo) | **GET** /url_lists/{id} | Get a URL list report |
| [**listCitationGroups**](SourcesCitationIntelligenceApi.md#listCitationGroups) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitationGroupsWithHttpInfo**](SourcesCitationIntelligenceApi.md#listCitationGroupsWithHttpInfo) | **GET** /citation_intelligence/groups | Grouped citation intelligence |
| [**listCitedUrlOccurrences**](SourcesCitationIntelligenceApi.md#listCitedUrlOccurrences) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**listCitedUrlOccurrencesWithHttpInfo**](SourcesCitationIntelligenceApi.md#listCitedUrlOccurrencesWithHttpInfo) | **GET** /citation_intelligence/urls/{url_sha256}/occurrences | Cited URL occurrences |
| [**listSources**](SourcesCitationIntelligenceApi.md#listSources) | **GET** /dimensions/sources | List source URLs |
| [**listSourcesWithHttpInfo**](SourcesCitationIntelligenceApi.md#listSourcesWithHttpInfo) | **GET** /dimensions/sources | List source URLs |
| [**listUrlLists**](SourcesCitationIntelligenceApi.md#listUrlLists) | **GET** /url_lists | List URL lists |
| [**listUrlListsWithHttpInfo**](SourcesCitationIntelligenceApi.md#listUrlListsWithHttpInfo) | **GET** /url_lists | List URL lists |
| [**removeUrlListEntries**](SourcesCitationIntelligenceApi.md#removeUrlListEntries) | **POST** /url_lists/{id}/entries/remove | Remove entries from a URL list |
| [**removeUrlListEntriesWithHttpInfo**](SourcesCitationIntelligenceApi.md#removeUrlListEntriesWithHttpInfo) | **POST** /url_lists/{id}/entries/remove | Remove entries from a URL list |
| [**updateUrlList**](SourcesCitationIntelligenceApi.md#updateUrlList) | **PATCH** /url_lists/{id} | Update a URL list |
| [**updateUrlListWithHttpInfo**](SourcesCitationIntelligenceApi.md#updateUrlListWithHttpInfo) | **PATCH** /url_lists/{id} | Update a URL list |



## addUrlListEntries

> UrlListEntriesAddResponse addUrlListEntries(id, urlListEntriesAddRequest)

Add entries to a URL list

Adds entries, as POST /url_lists reads them. A rule the list already holds keeps its place and takes only the added_on, cost and channel this request sends for it. Values that do not parse come back in invalid_entries. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListEntriesAddRequest urlListEntriesAddRequest = new UrlListEntriesAddRequest(); // UrlListEntriesAddRequest | 
        try {
            UrlListEntriesAddResponse result = apiInstance.addUrlListEntries(id, urlListEntriesAddRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#addUrlListEntries");
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
| **id** | **Integer**|  | |
| **urlListEntriesAddRequest** | [**UrlListEntriesAddRequest**](UrlListEntriesAddRequest.md)|  | |

### Return type

[**UrlListEntriesAddResponse**](UrlListEntriesAddResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entries written |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## addUrlListEntriesWithHttpInfo

> ApiResponse<UrlListEntriesAddResponse> addUrlListEntriesWithHttpInfo(id, urlListEntriesAddRequest)

Add entries to a URL list

Adds entries, as POST /url_lists reads them. A rule the list already holds keeps its place and takes only the added_on, cost and channel this request sends for it. Values that do not parse come back in invalid_entries. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListEntriesAddRequest urlListEntriesAddRequest = new UrlListEntriesAddRequest(); // UrlListEntriesAddRequest | 
        try {
            ApiResponse<UrlListEntriesAddResponse> response = apiInstance.addUrlListEntriesWithHttpInfo(id, urlListEntriesAddRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#addUrlListEntries");
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
| **id** | **Integer**|  | |
| **urlListEntriesAddRequest** | [**UrlListEntriesAddRequest**](UrlListEntriesAddRequest.md)|  | |

### Return type

ApiResponse<[**UrlListEntriesAddResponse**](UrlListEntriesAddResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entries written |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## createUrlList

> UrlListCreateResponse createUrlList(urlListCreateRequest)

Create a URL list

Creates a URL list. Each entry is a string or an object with value, match_type, added_on (YYYY-MM-DD, default today), cost (in the list currency) and channel. Without a match_type, \&quot;acme.com/blog/_*\&quot; is a prefix, a value with a path or query an exact URL and a bare host a domain. A list holds at most 1000 entries and a project at most 100 lists; the name is unique per project, case-insensitive. Refusals answer ERR_INVALID_PARAM with a reason token in error.meta.reason. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        UrlListCreateRequest urlListCreateRequest = new UrlListCreateRequest(); // UrlListCreateRequest | 
        try {
            UrlListCreateResponse result = apiInstance.createUrlList(urlListCreateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#createUrlList");
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
| **urlListCreateRequest** | [**UrlListCreateRequest**](UrlListCreateRequest.md)|  | |

### Return type

[**UrlListCreateResponse**](UrlListCreateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

## createUrlListWithHttpInfo

> ApiResponse<UrlListCreateResponse> createUrlListWithHttpInfo(urlListCreateRequest)

Create a URL list

Creates a URL list. Each entry is a string or an object with value, match_type, added_on (YYYY-MM-DD, default today), cost (in the list currency) and channel. Without a match_type, \&quot;acme.com/blog/_*\&quot; is a prefix, a value with a path or query an exact URL and a bare host a domain. A list holds at most 1000 entries and a project at most 100 lists; the name is unique per project, case-insensitive. Refusals answer ERR_INVALID_PARAM with a reason token in error.meta.reason. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        UrlListCreateRequest urlListCreateRequest = new UrlListCreateRequest(); // UrlListCreateRequest | 
        try {
            ApiResponse<UrlListCreateResponse> response = apiInstance.createUrlListWithHttpInfo(urlListCreateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#createUrlList");
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
| **urlListCreateRequest** | [**UrlListCreateRequest**](UrlListCreateRequest.md)|  | |

### Return type

ApiResponse<[**UrlListCreateResponse**](UrlListCreateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |


## deleteUrlList

> UrlListDeleteResponse deleteUrlList(projectId, id)

Delete a URL list

Deletes a URL list and its entries. Citation data is not affected. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            UrlListDeleteResponse result = apiInstance.deleteUrlList(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#deleteUrlList");
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

### Return type

[**UrlListDeleteResponse**](UrlListDeleteResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Deleted |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

## deleteUrlListWithHttpInfo

> ApiResponse<UrlListDeleteResponse> deleteUrlListWithHttpInfo(projectId, id)

Delete a URL list

Deletes a URL list and its entries. Citation data is not affected. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            ApiResponse<UrlListDeleteResponse> response = apiInstance.deleteUrlListWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#deleteUrlList");
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

### Return type

ApiResponse<[**UrlListDeleteResponse**](UrlListDeleteResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Deleted |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |


## getCitedUrlContent

> void getCitedUrlContent(projectId, urlSha256)

Cited URL cached content

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            apiInstance.getCitedUrlContent(projectId, urlSha256);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getCitedUrlContent");
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

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        try {
            ApiResponse<Void> response = apiInstance.getCitedUrlContentWithHttpInfo(projectId, urlSha256);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getCitedUrlContent");
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

> void getCitedUrlDetail(projectId, urlSha256, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, sourceType, sentiment, contentGap, includeSeries)

Cited URL detail

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. The filters narrow stats and citation_series alike. citation_series (with include_series&#x3D;true) holds the answers citing the URL under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
        Boolean includeSeries = false; // Boolean | Adds citation_series. Without it the response is unchanged.
        try {
            apiInstance.getCitedUrlDetail(projectId, urlSha256, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, sourceType, sentiment, contentGap, includeSeries);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getCitedUrlDetail");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] [enum: mentioned, gap] |
| **includeSeries** | **Boolean**| Adds citation_series. Without it the response is unchanged. | [optional] [default to false] |

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

> ApiResponse<Void> getCitedUrlDetailWithHttpInfo(projectId, urlSha256, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, sourceType, sentiment, contentGap, includeSeries)

Cited URL detail

Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. The filters narrow stats and citation_series alike. citation_series (with include_series&#x3D;true) holds the answers citing the URL under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
        Boolean includeSeries = false; // Boolean | Adds citation_series. Without it the response is unchanged.
        try {
            ApiResponse<Void> response = apiInstance.getCitedUrlDetailWithHttpInfo(projectId, urlSha256, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, sourceType, sentiment, contentGap, includeSeries);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getCitedUrlDetail");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] [enum: mentioned, gap] |
| **includeSeries** | **Boolean**| Adds citation_series. Without it the response is unchanged. | [optional] [default to false] |

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

> void getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to)

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
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        List<String> domains = Arrays.asList(); // List<String> | Source domains to analyze: one domain or a comma-separated list, e.g. domains=gmac.com,educaweb.com. The bracket form domains[]=gmac.com&domains[]=educaweb.com is also accepted.
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        try {
            apiInstance.getMentionsByCitingDomain(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getMentionsByCitingDomain");
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
| **domains** | [**List&lt;String&gt;**](String.md)| Source domains to analyze: one domain or a comma-separated list, e.g. domains&#x3D;gmac.com,educaweb.com. The bracket form domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com is also accepted. | |
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

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

> ApiResponse<Void> getMentionsByCitingDomainWithHttpInfo(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to)

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
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        List<String> domains = Arrays.asList(); // List<String> | Source domains to analyze: one domain or a comma-separated list, e.g. domains=gmac.com,educaweb.com. The bracket form domains[]=gmac.com&domains[]=educaweb.com is also accepted.
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        try {
            ApiResponse<Void> response = apiInstance.getMentionsByCitingDomainWithHttpInfo(projectId, domains, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getMentionsByCitingDomain");
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
| **domains** | [**List&lt;String&gt;**](String.md)| Source domains to analyze: one domain or a comma-separated list, e.g. domains&#x3D;gmac.com,educaweb.com. The bracket form domains[]&#x3D;gmac.com&amp;domains[]&#x3D;educaweb.com is also accepted. | |
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |

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


## getUrlList

> UrlListDetailResponse getUrlList(id, projectId, status, order, direction, page, perPage, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range)

Get a URL list report

The list, its summary (entries_count, cited_entries, citations, answers in the window, citation_rate, avg_citation_position, median_days_to_first_citation, total_cost, cost_per_cited_entry) and a page of its entries. An entry&#39;s status is cited (an answer cited it in the window), lost (cited before the window, not in it) or not_cited. first_cited_at reads the filtered answers up to the window&#39;s end. days_to_first_citation is null before the first citation or when the page was cited before it was added. brand_mentioned is set for exact URLs once their page was read, else null. Without from/to or range the window is all time. Requires the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        Integer projectId = 56; // Integer | Project ID
        String status = "cited"; // String | Only entries with this status.
        String order = "value"; // String | 
        String direction = "asc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            UrlListDetailResponse result = apiInstance.getUrlList(id, projectId, status, order, direction, page, perPage, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getUrlList");
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
| **id** | **Integer**|  | |
| **projectId** | **Integer**| Project ID | |
| **status** | **String**| Only entries with this status. | [optional] [enum: cited, lost, not_cited] |
| **order** | **String**|  | [optional] [default to citations] [enum: value, status, added_on, first_cited_at, days_to_cite, citations, avg_position, cost, channel] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**UrlListDetailResponse**](UrlListDetailResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | URL list report |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getUrlListWithHttpInfo

> ApiResponse<UrlListDetailResponse> getUrlListWithHttpInfo(id, projectId, status, order, direction, page, perPage, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range)

Get a URL list report

The list, its summary (entries_count, cited_entries, citations, answers in the window, citation_rate, avg_citation_position, median_days_to_first_citation, total_cost, cost_per_cited_entry) and a page of its entries. An entry&#39;s status is cited (an answer cited it in the window), lost (cited before the window, not in it) or not_cited. first_cited_at reads the filtered answers up to the window&#39;s end. days_to_first_citation is null before the first citation or when the page was cited before it was added. brand_mentioned is set for exact URLs once their page was read, else null. Without from/to or range the window is all time. Requires the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        Integer projectId = 56; // Integer | Project ID
        String status = "cited"; // String | Only entries with this status.
        String order = "value"; // String | 
        String direction = "asc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            ApiResponse<UrlListDetailResponse> response = apiInstance.getUrlListWithHttpInfo(id, projectId, status, order, direction, page, perPage, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#getUrlList");
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
| **id** | **Integer**|  | |
| **projectId** | **Integer**| Project ID | |
| **status** | **String**| Only entries with this status. | [optional] [enum: cited, lost, not_cited] |
| **order** | **String**|  | [optional] [default to citations] [enum: value, status, added_on, first_cited_at, days_to_cite, citations, avg_position, cost, channel] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

ApiResponse<[**UrlListDetailResponse**](UrlListDetailResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | URL list report |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## listCitationGroups

> void listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, key, includeSeries, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. Pass key to read one group; brand_kind filters by the brand focus of the prompts, like the source page. citation_series (with include_series&#x3D;true) holds the answers citing the URL, domain or host under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String view = "url"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String order = "group_key"; // String | 
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String key = "key_example"; // String | Return only this group of the chosen view: a domain (view=domain), a host (view=host) or a cited URL exactly as listed (view=url). Domains and hosts match case-insensitively, without www. A view=url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error.
        Boolean includeSeries = false; // Boolean | Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group's row.
        String query = "query_example"; // String | 
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
        try {
            apiInstance.listCitationGroups(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, key, includeSeries, query, sourceType, sentiment, contentGap);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listCitationGroups");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **key** | **String**| Return only this group of the chosen view: a domain (view&#x3D;domain), a host (view&#x3D;host) or a cited URL exactly as listed (view&#x3D;url). Domains and hosts match case-insensitively, without www. A view&#x3D;url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error. | [optional] |
| **includeSeries** | **Boolean**| Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group&#39;s row. | [optional] [default to false] |
| **query** | **String**|  | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] [enum: mentioned, gap] |

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

> ApiResponse<Void> listCitationGroupsWithHttpInfo(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, key, includeSeries, query, sourceType, sentiment, contentGap)

Grouped citation intelligence

Grouped citation intelligence by url / domain / host with per-model breakdown, citation rate, and avg citation position. Counts and citation rate include visible citations and background source references. Average position ignores rows with position&#x3D;0. Owned and competitor source matching honor the project&#39;s exact-subdomain setting. Filter vocabulary aligns with &#x60;source_type&#x60; returned by the API. Unavailable page content keeps the cited URL and citation metrics. Page metadata/content and unknown brand_mentioned/competitor_mentioned return null. content_gap_status is content_unavailable (or missing_page_cache) without usable content, and mentions_not_processed when the page has usable content but its mention analysis has not completed for this project. Mention fields (brand_mentioned, competitor_mentioned, brand_position, brands, mentions, content_gap_status) describe the analysis for the requesting project: a page not yet analyzed for it returns null (never false) brand_mentioned, competitor_mentioned and brand_position, empty brands and mentions arrays and page_cache.mentions_processed false. page_cache.mentions_processed is true exactly when brand_mentioned is not null. An analyzed page keeps its last result until a newer analysis replaces it. status_code shows a saved successful response or observed 404/410; other crawl failures and error_message are hidden. last_crawled_at dates the saved copy. Domain/host crawled_urls_count counts usable copies; brand_mentioned_urls_count and competitor_mentioned_urls_count count only URLs analyzed for the project and are null when none is. Pass key to read one group; brand_kind filters by the brand focus of the prompts, like the source page. citation_series (with include_series&#x3D;true) holds the answers citing the URL, domain or host under the same filters: granularity (day, week or month, from the account tracking cadence, with weeks when a daily account spans more than 60 days, starting on Monday), total (equal to total_responses), by_model (answers per AI model, largest first, which can include enabled models outside the seven the model filter accepts) and data, one { date, value } point per period that holds a filtered answer, so a zero means answers ran and none cited it. Periods date each answer by the day it was created in Europe/Madrid time, the date from and to filter.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String view = "url"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String order = "group_key"; // String | 
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String key = "key_example"; // String | Return only this group of the chosen view: a domain (view=domain), a host (view=host) or a cited URL exactly as listed (view=url). Domains and hosts match case-insensitively, without www. A view=url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error.
        Boolean includeSeries = false; // Boolean | Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group's row.
        String query = "query_example"; // String | 
        String sourceType = "owned"; // String | 
        String sentiment = "negative"; // String | 
        String contentGap = "mentioned"; // String | mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match.
        try {
            ApiResponse<Void> response = apiInstance.listCitationGroupsWithHttpInfo(projectId, view, page, perPage, order, direction, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, key, includeSeries, query, sourceType, sentiment, contentGap);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listCitationGroups");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **key** | **String**| Return only this group of the chosen view: a domain (view&#x3D;domain), a host (view&#x3D;host) or a cited URL exactly as listed (view&#x3D;url). Domains and hosts match case-insensitively, without www. A view&#x3D;url key is one raw URL, so its variants (a tracking parameter, a trailing slash) stay separate rows; GET /citation_intelligence/urls/{url_sha256} merges them, as the app does. No match returns an empty list (total 0), not an error. | [optional] |
| **includeSeries** | **Boolean**| Requires key, else 422 ERR_INVALID_PARAM. Adds citation_series to the group&#39;s row. | [optional] [default to false] |
| **query** | **String**|  | [optional] |
| **sourceType** | **String**|  | [optional] [enum: owned, competitor, third_party, social_media, own_domain, ugc, background] |
| **sentiment** | **String**|  | [optional] [enum: negative] |
| **contentGap** | **String**| mentioned: the cited page mentions your brand. gap: it mentions a competitor but not your brand. Only pages with usable content whose mention analysis has completed for this project match. | [optional] [enum: mentioned, gap] |

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
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.listCitedUrlOccurrences(projectId, urlSha256, page, perPage);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listCitedUrlOccurrences");
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
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String urlSha256 = "urlSha256_example"; // String | 64-character hex SHA-256 of the cited URL
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.listCitedUrlOccurrencesWithHttpInfo(projectId, urlSha256, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listCitedUrlOccurrences");
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


## listSources

> void listSources(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output, promptType, brandKind, range)

List source URLs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
        String sourceType = "owned"; // String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM.
        String mentionFilter = "mentions_you"; // String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            apiInstance.listSources(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output, promptType, brandKind, range);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listSources");
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
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **sourceType** | **String**| Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM. | [optional] [enum: owned, competitor, third_party] |
| **mentionFilter** | **String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **competitors** | **String**| Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

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
| **200** | Paginated sources |  -  |
| **422** | Invalid parameters |  -  |

## listSourcesWithHttpInfo

> ApiResponse<Void> listSourcesWithHttpInfo(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output, promptType, brandKind, range)

List source URLs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Filter by one AI model. It must be a model enabled for the API key's user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM.
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it.
        String sourceType = "owned"; // String | Filter by source ownership. Owned and competitor matching honor the project's exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM.
        String mentionFilter = "mentions_you"; // String | Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with 'competitors' to narrow the competitor side to specific rivals; on a negative cell that reads 'none of these'. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value 'competitors_only' is still accepted as an alias of competitor_not_you.
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM)
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            ApiResponse<Void> response = apiInstance.listSourcesWithHttpInfo(projectId, page, perPage, model, collectionId, countryCode, languageCode, prompt, from, to, sourceType, mentionFilter, competitors, output, promptType, brandKind, range);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listSources");
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
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Filter by one AI model. It must be a model enabled for the API key&#39;s user: an unknown value, or a model the user has not enabled, returns 422 ERR_INVALID_PARAM with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **from** | **OffsetDateTime**| Start of the window. Sent alone, the window runs from it to the end of today. A from later than to, or a window longer than 1,500 days, returns 422 ERR_INVALID_PARAM. | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. Sent without from, the window covers the 30 days that end on it. | [optional] |
| **sourceType** | **String**| Filter by source ownership. Owned and competitor matching honor the project&#39;s exact-subdomain setting. Any other value, including a differently cased one, returns ERR_INVALID_PARAM. | [optional] [enum: owned, competitor, third_party] |
| **mentionFilter** | **String**| Filter by which brands are mentioned, as a two-axis matrix (your brand x competitors): mentions_you / not_mentions_you, mentions_competitor / not_mentions_competitor, and the four combined cells you_and_competitor, competitor_not_you (a rival wins and you are absent), you_not_competitor, no_brands (no tracked brand appears, i.e. open space; on answers, finished answers only). Combine with &#39;competitors&#39; to narrow the competitor side to specific rivals; on a negative cell that reads &#39;none of these&#39;. On /dimensions/sources it applies to the crawled content of each cited page instead of the answer text. The legacy value &#39;competitors_only&#39; is still accepted as an alias of competitor_not_you. | [optional] [enum: mentions_you, not_mentions_you, mentions_competitor, not_mentions_competitor, you_and_competitor, competitor_not_you, you_not_competitor, no_brands] |
| **competitors** | **String**| Comma-separated competitor IDs (a malformed or unknown ID returns ERR_INVALID_PARAM) | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

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
| **200** | Paginated sources |  -  |
| **422** | Invalid parameters |  -  |


## listUrlLists

> UrlListsResponse listUrlLists(projectId, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range)

List URL lists

A URL list is a named set of rules, each an exact URL (matched over http and https, with or without www), a URL prefix (every page under host/path) or a domain (the site and its subdomains). Its numbers count the AI answers to the prompts tracked in the project: cited_entries is the entries an answer cited in the window and citations the answers citing any entry, each once. Without from/to or range the window is all time. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            UrlListsResponse result = apiInstance.listUrlLists(projectId, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listUrlLists");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

[**UrlListsResponse**](UrlListsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | URL lists |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |

## listUrlListsWithHttpInfo

> ApiResponse<UrlListsResponse> listUrlListsWithHttpInfo(projectId, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range)

List URL lists

A URL list is a named set of rules, each an exact URL (matched over http and https, with or without www), a URL prefix (every page under host/path) or a domain (the site and its subdomains). Its numbers count the AI answers to the prompts tracked in the project: cited_entries is the entries an answer cited in the window and citations the answers citing any entry, each once. Without from/to or range the window is all time. Requires the Growth plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String model = "chatgpt"; // String | Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key's user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM.
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to.
        try {
            ApiResponse<UrlListsResponse> response = apiInstance.listUrlListsWithHttpInfo(projectId, model, collectionId, countryCode, languageCode, prompt, brandKind, from, to, range);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#listUrlLists");
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
| **model** | **String**| Filter by one AI model. Only chatgpt, ai_overview, ai_mode, perplexity, gemini, naver_ai, baidu_ai, naver_ai_tab, qwen, doubao and bing_ai_mode are accepted: any other value, including another model enabled for the API key&#39;s user, returns 422 ERR_INVALID_PARAM (invalid model). One of those eleven that the user has not enabled also returns 422 ERR_INVALID_PARAM, with the valid values in the message. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai, naver_ai_tab, qwen, doubao, bing_ai_mode] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID. An id that is not a plain positive number, or that names no prompt of the project, returns 422 ERR_INVALID_PARAM. | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **range** | **Integer**| Number of days to look back (alternative to from/to, which win when both are given). A value that is not a plain positive number returns 422 ERR_INVALID_PARAM, even beside from/to. | [optional] |

### Return type

ApiResponse<[**UrlListsResponse**](UrlListsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | URL lists |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **422** | Invalid parameters |  -  |


## removeUrlListEntries

> UrlListEntriesRemoveResponse removeUrlListEntries(id, urlListEntriesRemoveRequest)

Remove entries from a URL list

Removes entries by id (from GET /url_lists/{id}) or by value as written (\&quot;https://acme.com/a\&quot;, \&quot;acme.com/blog/_*\&quot;, \&quot;acme.com\&quot;). Sending neither answers ERR_INVALID_PARAM. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListEntriesRemoveRequest urlListEntriesRemoveRequest = new UrlListEntriesRemoveRequest(); // UrlListEntriesRemoveRequest | 
        try {
            UrlListEntriesRemoveResponse result = apiInstance.removeUrlListEntries(id, urlListEntriesRemoveRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#removeUrlListEntries");
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
| **id** | **Integer**|  | |
| **urlListEntriesRemoveRequest** | [**UrlListEntriesRemoveRequest**](UrlListEntriesRemoveRequest.md)|  | |

### Return type

[**UrlListEntriesRemoveResponse**](UrlListEntriesRemoveResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entries removed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## removeUrlListEntriesWithHttpInfo

> ApiResponse<UrlListEntriesRemoveResponse> removeUrlListEntriesWithHttpInfo(id, urlListEntriesRemoveRequest)

Remove entries from a URL list

Removes entries by id (from GET /url_lists/{id}) or by value as written (\&quot;https://acme.com/a\&quot;, \&quot;acme.com/blog/_*\&quot;, \&quot;acme.com\&quot;). Sending neither answers ERR_INVALID_PARAM. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListEntriesRemoveRequest urlListEntriesRemoveRequest = new UrlListEntriesRemoveRequest(); // UrlListEntriesRemoveRequest | 
        try {
            ApiResponse<UrlListEntriesRemoveResponse> response = apiInstance.removeUrlListEntriesWithHttpInfo(id, urlListEntriesRemoveRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#removeUrlListEntries");
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
| **id** | **Integer**|  | |
| **urlListEntriesRemoveRequest** | [**UrlListEntriesRemoveRequest**](UrlListEntriesRemoveRequest.md)|  | |

### Return type

ApiResponse<[**UrlListEntriesRemoveResponse**](UrlListEntriesRemoveResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entries removed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## updateUrlList

> UrlListUpdateResponse updateUrlList(id, urlListUpdateRequest)

Update a URL list

Changes the name, description or currency of a URL list. Entries are added with POST /url_lists/{id}/entries and removed with POST /url_lists/{id}/entries/remove. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListUpdateRequest urlListUpdateRequest = new UrlListUpdateRequest(); // UrlListUpdateRequest | 
        try {
            UrlListUpdateResponse result = apiInstance.updateUrlList(id, urlListUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#updateUrlList");
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
| **id** | **Integer**|  | |
| **urlListUpdateRequest** | [**UrlListUpdateRequest**](UrlListUpdateRequest.md)|  | |

### Return type

[**UrlListUpdateResponse**](UrlListUpdateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateUrlListWithHttpInfo

> ApiResponse<UrlListUpdateResponse> updateUrlListWithHttpInfo(id, urlListUpdateRequest)

Update a URL list

Changes the name, description or currency of a URL list. Entries are added with POST /url_lists/{id}/entries and removed with POST /url_lists/{id}/entries/remove. Requires a &#x60;read_write&#x60; scope API key and the Growth plan.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.SourcesCitationIntelligenceApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        SourcesCitationIntelligenceApi apiInstance = new SourcesCitationIntelligenceApi(defaultClient);
        Integer id = 56; // Integer | 
        UrlListUpdateRequest urlListUpdateRequest = new UrlListUpdateRequest(); // UrlListUpdateRequest | 
        try {
            ApiResponse<UrlListUpdateResponse> response = apiInstance.updateUrlListWithHttpInfo(id, urlListUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling SourcesCitationIntelligenceApi#updateUrlList");
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
| **id** | **Integer**|  | |
| **urlListUpdateRequest** | [**UrlListUpdateRequest**](UrlListUpdateRequest.md)|  | |

### Return type

ApiResponse<[**UrlListUpdateResponse**](UrlListUpdateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

