# GeoWriterApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createIntelligenceTask**](GeoWriterApi.md#createIntelligenceTask) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**createIntelligenceTaskWithHttpInfo**](GeoWriterApi.md#createIntelligenceTaskWithHttpInfo) | **POST** /intelligence_tasks | Create a GEO Writer task |
| [**getIntelligenceTask**](GeoWriterApi.md#getIntelligenceTask) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**getIntelligenceTaskWithHttpInfo**](GeoWriterApi.md#getIntelligenceTaskWithHttpInfo) | **GET** /intelligence_tasks/{id} | Get a GEO Writer task |
| [**listIntelligenceTasks**](GeoWriterApi.md#listIntelligenceTasks) | **GET** /intelligence_tasks | List GEO Writer tasks |
| [**listIntelligenceTasksWithHttpInfo**](GeoWriterApi.md#listIntelligenceTasksWithHttpInfo) | **GET** /intelligence_tasks | List GEO Writer tasks |



## createIntelligenceTask

> IntelligenceTask createIntelligenceTask(intelligenceTaskCreateRequest)

Create a GEO Writer task

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        IntelligenceTaskCreateRequest intelligenceTaskCreateRequest = new IntelligenceTaskCreateRequest(); // IntelligenceTaskCreateRequest | 
        try {
            IntelligenceTask result = apiInstance.createIntelligenceTask(intelligenceTaskCreateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#createIntelligenceTask");
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
| **intelligenceTaskCreateRequest** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md)|  | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **422** | Invalid parameters |  -  |

## createIntelligenceTaskWithHttpInfo

> ApiResponse<IntelligenceTask> createIntelligenceTaskWithHttpInfo(intelligenceTaskCreateRequest)

Create a GEO Writer task

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        IntelligenceTaskCreateRequest intelligenceTaskCreateRequest = new IntelligenceTaskCreateRequest(); // IntelligenceTaskCreateRequest | 
        try {
            ApiResponse<IntelligenceTask> response = apiInstance.createIntelligenceTaskWithHttpInfo(intelligenceTaskCreateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#createIntelligenceTask");
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
| **intelligenceTaskCreateRequest** | [**IntelligenceTaskCreateRequest**](IntelligenceTaskCreateRequest.md)|  | |

### Return type

ApiResponse<[**IntelligenceTask**](IntelligenceTask.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created |  -  |
| **422** | Invalid parameters |  -  |


## getIntelligenceTask

> IntelligenceTask getIntelligenceTask(projectId, id)

Get a GEO Writer task

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Numeric task ID or public_id string token
        try {
            IntelligenceTask result = apiInstance.getIntelligenceTask(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#getIntelligenceTask");
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
| **id** | **String**| Numeric task ID or public_id string token | |

### Return type

[**IntelligenceTask**](IntelligenceTask.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Task with result_data when completed |  -  |

## getIntelligenceTaskWithHttpInfo

> ApiResponse<IntelligenceTask> getIntelligenceTaskWithHttpInfo(projectId, id)

Get a GEO Writer task

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Numeric task ID or public_id string token
        try {
            ApiResponse<IntelligenceTask> response = apiInstance.getIntelligenceTaskWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#getIntelligenceTask");
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
| **id** | **String**| Numeric task ID or public_id string token | |

### Return type

ApiResponse<[**IntelligenceTask**](IntelligenceTask.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Task with result_data when completed |  -  |


## listIntelligenceTasks

> void listIntelligenceTasks(projectId, taskType, status, page, perPage)

List GEO Writer tasks

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String taskType = "brief"; // String | 
        String status = "status_example"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.listIntelligenceTasks(projectId, taskType, status, page, perPage);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#listIntelligenceTasks");
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
| **taskType** | **String**|  | [optional] [enum: brief, create, update, pr_insights, custom] |
| **status** | **String**|  | [optional] |
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
| **200** | Paginated tasks |  -  |

## listIntelligenceTasksWithHttpInfo

> ApiResponse<Void> listIntelligenceTasksWithHttpInfo(projectId, taskType, status, page, perPage)

List GEO Writer tasks

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoWriterApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoWriterApi apiInstance = new GeoWriterApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String taskType = "brief"; // String | 
        String status = "status_example"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.listIntelligenceTasksWithHttpInfo(projectId, taskType, status, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#listIntelligenceTasks");
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
| **taskType** | **String**|  | [optional] [enum: brief, create, update, pr_insights, custom] |
| **status** | **String**|  | [optional] |
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
| **200** | Paginated tasks |  -  |

