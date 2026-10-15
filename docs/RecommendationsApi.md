# RecommendationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getRecommendation**](RecommendationsApi.md#getRecommendation) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**getRecommendationWithHttpInfo**](RecommendationsApi.md#getRecommendationWithHttpInfo) | **GET** /recommendations/{id} | Get recommendation run with items |
| [**launchRecommendations**](RecommendationsApi.md#launchRecommendations) | **POST** /recommendations | Launch a recommendations generation |
| [**launchRecommendationsWithHttpInfo**](RecommendationsApi.md#launchRecommendationsWithHttpInfo) | **POST** /recommendations | Launch a recommendations generation |
| [**listRecommendations**](RecommendationsApi.md#listRecommendations) | **GET** /recommendations | List recommendation runs |
| [**listRecommendationsWithHttpInfo**](RecommendationsApi.md#listRecommendationsWithHttpInfo) | **GET** /recommendations | List recommendation runs |
| [**updateRecommendationItem**](RecommendationsApi.md#updateRecommendationItem) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |
| [**updateRecommendationItemWithHttpInfo**](RecommendationsApi.md#updateRecommendationItemWithHttpInfo) | **PATCH** /recommendations/{id}/items/{item_id} | Complete, archive or restore a recommendation item |



## getRecommendation

> void getRecommendation(projectId, id, itemStatus, resolveSourceRefs)

Get recommendation run with items

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        String itemStatus = "active"; // String | 
        Boolean resolveSourceRefs = true; // Boolean | 
        try {
            apiInstance.getRecommendation(projectId, id, itemStatus, resolveSourceRefs);
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#getRecommendation");
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
| **itemStatus** | **String**|  | [optional] [enum: active, completed, archived] |
| **resolveSourceRefs** | **Boolean**|  | [optional] [default to true] |

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
| **200** | Recommendation detail with items |  -  |
| **404** | Resource not found |  -  |

## getRecommendationWithHttpInfo

> ApiResponse<Void> getRecommendationWithHttpInfo(projectId, id, itemStatus, resolveSourceRefs)

Get recommendation run with items

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        String itemStatus = "active"; // String | 
        Boolean resolveSourceRefs = true; // Boolean | 
        try {
            ApiResponse<Void> response = apiInstance.getRecommendationWithHttpInfo(projectId, id, itemStatus, resolveSourceRefs);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#getRecommendation");
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
| **itemStatus** | **String**|  | [optional] [enum: active, completed, archived] |
| **resolveSourceRefs** | **Boolean**|  | [optional] [default to true] |

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
| **200** | Recommendation detail with items |  -  |
| **404** | Resource not found |  -  |


## launchRecommendations

> void launchRecommendations(launchRecommendationsRequest)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        LaunchRecommendationsRequest launchRecommendationsRequest = new LaunchRecommendationsRequest(); // LaunchRecommendationsRequest | 
        try {
            apiInstance.launchRecommendations(launchRecommendationsRequest);
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#launchRecommendations");
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
| **launchRecommendationsRequest** | [**LaunchRecommendationsRequest**](LaunchRecommendationsRequest.md)|  | |

### Return type


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Generation launched (status pending) |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

## launchRecommendationsWithHttpInfo

> ApiResponse<Void> launchRecommendationsWithHttpInfo(launchRecommendationsRequest)

Launch a recommendations generation

Launches a full-scope recommendations generation (async job, 1-3 minutes; poll GET /recommendations/{id} until status is completed). Consumes the project weekly recommendation-item budget: returns ERR_LIMIT_REACHED when it is exhausted or when a generation of the same type is already pending/processing. sentiment_reputation requires the Scale plan or above. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        LaunchRecommendationsRequest launchRecommendationsRequest = new LaunchRecommendationsRequest(); // LaunchRecommendationsRequest | 
        try {
            ApiResponse<Void> response = apiInstance.launchRecommendationsWithHttpInfo(launchRecommendationsRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#launchRecommendations");
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
| **launchRecommendationsRequest** | [**LaunchRecommendationsRequest**](LaunchRecommendationsRequest.md)|  | |

### Return type


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Generation launched (status pending) |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |


## listRecommendations

> RecommendationsResponse listRecommendations(projectId, recommendationType, status, page, perPage)

List recommendation runs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String recommendationType = "ai_visibility"; // String | 
        String status = "pending"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            RecommendationsResponse result = apiInstance.listRecommendations(projectId, recommendationType, status, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#listRecommendations");
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
| **recommendationType** | **String**|  | [optional] [enum: ai_visibility, social_community, brand_building, sentiment_reputation] |
| **status** | **String**|  | [optional] [enum: pending, processing, completed, failed] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**RecommendationsResponse**](RecommendationsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated recommendations |  -  |

## listRecommendationsWithHttpInfo

> ApiResponse<RecommendationsResponse> listRecommendationsWithHttpInfo(projectId, recommendationType, status, page, perPage)

List recommendation runs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String recommendationType = "ai_visibility"; // String | 
        String status = "pending"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<RecommendationsResponse> response = apiInstance.listRecommendationsWithHttpInfo(projectId, recommendationType, status, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#listRecommendations");
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
| **recommendationType** | **String**|  | [optional] [enum: ai_visibility, social_community, brand_building, sentiment_reputation] |
| **status** | **String**|  | [optional] [enum: pending, processing, completed, failed] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**RecommendationsResponse**](RecommendationsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated recommendations |  -  |


## updateRecommendationItem

> RecommendationItemUpdateResponse updateRecommendationItem(id, itemId, updateRecommendationItemRequest)

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between &#x60;active&#x60;, &#x60;completed&#x60; and &#x60;archived&#x60;, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps &#x60;status_changed_at&#x60;. Returns the item in the shape &#x60;GET /recommendations/{id}&#x60; lists items. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer id = 56; // Integer | Recommendation run id
        Integer itemId = 56; // Integer | Item id, from the items of GET /recommendations/{id}
        UpdateRecommendationItemRequest updateRecommendationItemRequest = new UpdateRecommendationItemRequest(); // UpdateRecommendationItemRequest | 
        try {
            RecommendationItemUpdateResponse result = apiInstance.updateRecommendationItem(id, itemId, updateRecommendationItemRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#updateRecommendationItem");
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
| **id** | **Integer**| Recommendation run id | |
| **itemId** | **Integer**| Item id, from the items of GET /recommendations/{id} | |
| **updateRecommendationItemRequest** | [**UpdateRecommendationItemRequest**](UpdateRecommendationItemRequest.md)|  | |

### Return type

[**RecommendationItemUpdateResponse**](RecommendationItemUpdateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated item |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateRecommendationItemWithHttpInfo

> ApiResponse<RecommendationItemUpdateResponse> updateRecommendationItemWithHttpInfo(id, itemId, updateRecommendationItemRequest)

Complete, archive or restore a recommendation item

Moves one item of a recommendation run between &#x60;active&#x60;, &#x60;completed&#x60; and &#x60;archived&#x60;, exactly like the complete, archive and restore buttons on the Recommendations page, and stamps &#x60;status_changed_at&#x60;. Returns the item in the shape &#x60;GET /recommendations/{id}&#x60; lists items. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on Recommendations (the permission the page uses for these buttons).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.RecommendationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        RecommendationsApi apiInstance = new RecommendationsApi(defaultClient);
        Integer id = 56; // Integer | Recommendation run id
        Integer itemId = 56; // Integer | Item id, from the items of GET /recommendations/{id}
        UpdateRecommendationItemRequest updateRecommendationItemRequest = new UpdateRecommendationItemRequest(); // UpdateRecommendationItemRequest | 
        try {
            ApiResponse<RecommendationItemUpdateResponse> response = apiInstance.updateRecommendationItemWithHttpInfo(id, itemId, updateRecommendationItemRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling RecommendationsApi#updateRecommendationItem");
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
| **id** | **Integer**| Recommendation run id | |
| **itemId** | **Integer**| Item id, from the items of GET /recommendations/{id} | |
| **updateRecommendationItemRequest** | [**UpdateRecommendationItemRequest**](UpdateRecommendationItemRequest.md)|  | |

### Return type

ApiResponse<[**RecommendationItemUpdateResponse**](RecommendationItemUpdateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated item |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

