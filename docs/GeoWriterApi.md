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
| [**revertIntelligenceTaskContent**](GeoWriterApi.md#revertIntelligenceTaskContent) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**revertIntelligenceTaskContentWithHttpInfo**](GeoWriterApi.md#revertIntelligenceTaskContentWithHttpInfo) | **POST** /intelligence_tasks/{id}/revert | Revert GEO Writer task content |
| [**updateIntelligenceTaskContent**](GeoWriterApi.md#updateIntelligenceTaskContent) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |
| [**updateIntelligenceTaskContentWithHttpInfo**](GeoWriterApi.md#updateIntelligenceTaskContentWithHttpInfo) | **PATCH** /intelligence_tasks/{id} | Edit GEO Writer task content |



## createIntelligenceTask

> IntelligenceTask createIntelligenceTask(intelligenceTaskCreateRequest)

Create a GEO Writer task

Creates a GEO Writer task, processed asynchronously: poll GET /intelligence_tasks/{id} until status is completed. Prompt-based mode takes prompt_id; agentic mode takes custom_topic and/or user_instructions. task_type product_listing is API-only and serves store apps: send a product object (title required) and optionally prompt_ids, and the completed result_data holds ready-to-apply product page copy. Edit and revert it with PATCH /intelligence_tasks/{id} and POST /intelligence_tasks/{id}/revert. Requires a &#x60;read_write&#x60; scope API key.

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
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

## createIntelligenceTaskWithHttpInfo

> ApiResponse<IntelligenceTask> createIntelligenceTaskWithHttpInfo(intelligenceTaskCreateRequest)

Create a GEO Writer task

Creates a GEO Writer task, processed asynchronously: poll GET /intelligence_tasks/{id} until status is completed. Prompt-based mode takes prompt_id; agentic mode takes custom_topic and/or user_instructions. task_type product_listing is API-only and serves store apps: send a product object (title required) and optionally prompt_ids, and the completed result_data holds ready-to-apply product page copy. Edit and revert it with PATCH /intelligence_tasks/{id} and POST /intelligence_tasks/{id}/revert. Requires a &#x60;read_write&#x60; scope API key.

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
| **403** | API key lacks write permission |  -  |
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

> IntelligenceTasksResponse listIntelligenceTasks(projectId, taskType, status, page, perPage)

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
            IntelligenceTasksResponse result = apiInstance.listIntelligenceTasks(projectId, taskType, status, page, perPage);
            System.out.println(result);
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
| **taskType** | **String**|  | [optional] [enum: brief, create, update, pr_insights, custom, product_listing] |
| **status** | **String**|  | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**IntelligenceTasksResponse**](IntelligenceTasksResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tasks |  -  |

## listIntelligenceTasksWithHttpInfo

> ApiResponse<IntelligenceTasksResponse> listIntelligenceTasksWithHttpInfo(projectId, taskType, status, page, perPage)

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
            ApiResponse<IntelligenceTasksResponse> response = apiInstance.listIntelligenceTasksWithHttpInfo(projectId, taskType, status, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
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
| **taskType** | **String**|  | [optional] [enum: brief, create, update, pr_insights, custom, product_listing] |
| **status** | **String**|  | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**IntelligenceTasksResponse**](IntelligenceTasksResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated tasks |  -  |


## revertIntelligenceTaskContent

> IntelligenceTask revertIntelligenceTaskContent(projectId, id)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

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
            IntelligenceTask result = apiInstance.revertIntelligenceTaskContent(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#revertIntelligenceTaskContent");
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
| **200** | Task restored to its generated output |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## revertIntelligenceTaskContentWithHttpInfo

> ApiResponse<IntelligenceTask> revertIntelligenceTaskContentWithHttpInfo(projectId, id)

Revert GEO Writer task content

Discards every manual edit on the task and restores the output exactly as it was generated. Returns ERR_INVALID_PARAM when the task has no manual edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

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
            ApiResponse<IntelligenceTask> response = apiInstance.revertIntelligenceTaskContentWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#revertIntelligenceTaskContent");
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
| **200** | Task restored to its generated output |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## updateIntelligenceTaskContent

> IntelligenceTaskUpdateResponse updateIntelligenceTaskContent(id, intelligenceTaskUpdateRequest)

Edit GEO Writer task content

Edits the text of a completed task in place. &#x60;edits&#x60; maps dotted paths into result_data (for example &#x60;title&#x60; or &#x60;sections.0.content&#x60;) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank &#x60;title&#x60;, a value over 20,000 characters or an empty &#x60;edits&#x60; object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

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
        String id = "id_example"; // String | Numeric task ID or public_id string token
        IntelligenceTaskUpdateRequest intelligenceTaskUpdateRequest = new IntelligenceTaskUpdateRequest(); // IntelligenceTaskUpdateRequest | 
        try {
            IntelligenceTaskUpdateResponse result = apiInstance.updateIntelligenceTaskContent(id, intelligenceTaskUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#updateIntelligenceTaskContent");
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
| **id** | **String**| Numeric task ID or public_id string token | |
| **intelligenceTaskUpdateRequest** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md)|  | |

### Return type

[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated task with the paths that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateIntelligenceTaskContentWithHttpInfo

> ApiResponse<IntelligenceTaskUpdateResponse> updateIntelligenceTaskContentWithHttpInfo(id, intelligenceTaskUpdateRequest)

Edit GEO Writer task content

Edits the text of a completed task in place. &#x60;edits&#x60; maps dotted paths into result_data (for example &#x60;title&#x60; or &#x60;sections.0.content&#x60;) to replacement text. Only string fields that already exist can change: a path that does not resolve to text, a blank &#x60;title&#x60;, a value over 20,000 characters or an empty &#x60;edits&#x60; object is rejected with ERR_INVALID_PARAM and nothing is written. Values identical to the stored text are ignored, and the response lists the paths that actually changed. The first edit keeps a copy of the generated output so POST /intelligence_tasks/{id}/revert can restore it; regenerating the task replaces the edited content. Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Writer.

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
        String id = "id_example"; // String | Numeric task ID or public_id string token
        IntelligenceTaskUpdateRequest intelligenceTaskUpdateRequest = new IntelligenceTaskUpdateRequest(); // IntelligenceTaskUpdateRequest | 
        try {
            ApiResponse<IntelligenceTaskUpdateResponse> response = apiInstance.updateIntelligenceTaskContentWithHttpInfo(id, intelligenceTaskUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoWriterApi#updateIntelligenceTaskContent");
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
| **id** | **String**| Numeric task ID or public_id string token | |
| **intelligenceTaskUpdateRequest** | [**IntelligenceTaskUpdateRequest**](IntelligenceTaskUpdateRequest.md)|  | |

### Return type

ApiResponse<[**IntelligenceTaskUpdateResponse**](IntelligenceTaskUpdateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Updated task with the paths that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

