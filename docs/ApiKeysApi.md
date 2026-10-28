# ApiKeysApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createApiKey**](ApiKeysApi.md#createApiKey) | **POST** /api_keys | Create an API key limited to projects |
| [**createApiKeyWithHttpInfo**](ApiKeysApi.md#createApiKeyWithHttpInfo) | **POST** /api_keys | Create an API key limited to projects |
| [**listApiKeys**](ApiKeysApi.md#listApiKeys) | **GET** /api_keys | List API keys |
| [**listApiKeysWithHttpInfo**](ApiKeysApi.md#listApiKeysWithHttpInfo) | **GET** /api_keys | List API keys |
| [**revokeApiKey**](ApiKeysApi.md#revokeApiKey) | **DELETE** /api_keys/{id} | Revoke an API key |
| [**revokeApiKeyWithHttpInfo**](ApiKeysApi.md#revokeApiKeyWithHttpInfo) | **DELETE** /api_keys/{id} | Revoke an API key |



## createApiKey

> CreateApiKey201Response createApiKey(createApiKeyRequest)

Create an API key limited to projects

Creates an API key limited to the projects in project_ids, owned by the same user as the calling key, and returns its secret token once: store it, since it cannot be read again. The key sees only those projects (any other project answers ERR_PROJECT_NOT_FOUND) and cannot act on the whole account, and the set of projects never changes. This endpoint never creates an account-wide key; create one in the app under API Keys. scope is read (default) or read_write. Every project must be one the caller can access: a project of another account, a deleted one or an unknown id answers ERR_PROJECT_NOT_FOUND and nothing is created. A user can hold up to 500 active keys; past that the request answers ERR_LIMIT_REACHED until a key is revoked. Requires an account-wide &#x60;read_write&#x60; scope API key on the Scale plan or above: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to create API keys and can only choose projects they can access.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        CreateApiKeyRequest createApiKeyRequest = new CreateApiKeyRequest(); // CreateApiKeyRequest | 
        try {
            CreateApiKey201Response result = apiInstance.createApiKey(createApiKeyRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#createApiKey");
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
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md)|  | |

### Return type

[**CreateApiKey201Response**](CreateApiKey201Response.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The key as GET /api_keys lists it, plus its secret token, returned only this once. |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## createApiKeyWithHttpInfo

> ApiResponse<CreateApiKey201Response> createApiKeyWithHttpInfo(createApiKeyRequest)

Create an API key limited to projects

Creates an API key limited to the projects in project_ids, owned by the same user as the calling key, and returns its secret token once: store it, since it cannot be read again. The key sees only those projects (any other project answers ERR_PROJECT_NOT_FOUND) and cannot act on the whole account, and the set of projects never changes. This endpoint never creates an account-wide key; create one in the app under API Keys. scope is read (default) or read_write. Every project must be one the caller can access: a project of another account, a deleted one or an unknown id answers ERR_PROJECT_NOT_FOUND and nothing is created. A user can hold up to 500 active keys; past that the request answers ERR_LIMIT_REACHED until a key is revoked. Requires an account-wide &#x60;read_write&#x60; scope API key on the Scale plan or above: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. A team member needs permission to create API keys and can only choose projects they can access.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        CreateApiKeyRequest createApiKeyRequest = new CreateApiKeyRequest(); // CreateApiKeyRequest | 
        try {
            ApiResponse<CreateApiKey201Response> response = apiInstance.createApiKeyWithHttpInfo(createApiKeyRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#createApiKey");
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
| **createApiKeyRequest** | [**CreateApiKeyRequest**](CreateApiKeyRequest.md)|  | |

### Return type

ApiResponse<[**CreateApiKey201Response**](CreateApiKey201Response.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The key as GET /api_keys lists it, plus its secret token, returned only this once. |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## listApiKeys

> ListApiKeys200Response listApiKeys(page, perPage)

List API keys

Lists the API keys of the user the calling key belongs to, newest first, revoked ones included: name, the visible prefix of the token, scope (read or read_write), the projects a key is limited to (project_scoped, project_ids; an empty list on an account-wide key), when it was created and last used, and when it was revoked. The secret token is only ever returned once, by POST /api_keys. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan, so old keys can be found and revoked. A team member needs the API Keys permission and sees only their own keys.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        Integer page = 56; // Integer | 
        Integer perPage = 56; // Integer | Default 20, max 100
        try {
            ListApiKeys200Response result = apiInstance.listApiKeys(page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#listApiKeys");
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
| **page** | **Integer**|  | [optional] |
| **perPage** | **Integer**| Default 20, max 100 | [optional] |

### Return type

[**ListApiKeys200Response**](ListApiKeys200Response.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |

## listApiKeysWithHttpInfo

> ApiResponse<ListApiKeys200Response> listApiKeysWithHttpInfo(page, perPage)

List API keys

Lists the API keys of the user the calling key belongs to, newest first, revoked ones included: name, the visible prefix of the token, scope (read or read_write), the projects a key is limited to (project_scoped, project_ids; an empty list on an account-wide key), when it was created and last used, and when it was revoked. The secret token is only ever returned once, by POST /api_keys. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan, so old keys can be found and revoked. A team member needs the API Keys permission and sees only their own keys.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        Integer page = 56; // Integer | 
        Integer perPage = 56; // Integer | Default 20, max 100
        try {
            ApiResponse<ListApiKeys200Response> response = apiInstance.listApiKeysWithHttpInfo(page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#listApiKeys");
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
| **page** | **Integer**|  | [optional] |
| **perPage** | **Integer**| Default 20, max 100 | [optional] |

### Return type

ApiResponse<[**ListApiKeys200Response**](ListApiKeys200Response.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |


## revokeApiKey

> RevokeApiKey200Response revokeApiKey(id)

Revoke an API key

Revokes an API key of the user the calling key belongs to: it stops working immediately and cannot be restored. Revoking a key that is already revoked answers the same way and keeps its original revocation time. A key of another user answers ERR_NOT_FOUND. The calling key can revoke itself. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan. A team member needs permission to delete API keys.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        Integer id = 56; // Integer | The key id from GET /api_keys
        try {
            RevokeApiKey200Response result = apiInstance.revokeApiKey(id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#revokeApiKey");
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
| **id** | **Integer**| The key id from GET /api_keys | |

### Return type

[**RevokeApiKey200Response**](RevokeApiKey200Response.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |

## revokeApiKeyWithHttpInfo

> ApiResponse<RevokeApiKey200Response> revokeApiKeyWithHttpInfo(id)

Revoke an API key

Revokes an API key of the user the calling key belongs to: it stops working immediately and cannot be restored. Revoking a key that is already revoked answers the same way and keeps its original revocation time. A key of another user answers ERR_NOT_FOUND. The calling key can revoke itself. Requires an account-wide &#x60;read_write&#x60; scope API key: a key limited to some projects answers ERR_KEY_PROJECT_SCOPED. Still answers after the account moves below the Scale plan. A team member needs permission to delete API keys.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ApiKeysApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ApiKeysApi apiInstance = new ApiKeysApi(defaultClient);
        Integer id = 56; // Integer | The key id from GET /api_keys
        try {
            ApiResponse<RevokeApiKey200Response> response = apiInstance.revokeApiKeyWithHttpInfo(id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling ApiKeysApi#revokeApiKey");
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
| **id** | **Integer**| The key id from GET /api_keys | |

### Return type

ApiResponse<[**RevokeApiKey200Response**](RevokeApiKey200Response.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | A key limited to some projects answers ERR_KEY_PROJECT_SCOPED and a read-only key ERR_INSUFFICIENT_SCOPE: managing keys needs an account-wide read and write key. A team member without the API Keys permission answers ERR_INSUFFICIENT_PERMISSION, and creating a key below the Scale plan ERR_PLAN_REQUIRED, with the same status |  -  |
| **404** | Resource not found |  -  |

