# StoreIntegrationsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**acceptCatalogPromptSuggestions**](StoreIntegrationsApi.md#acceptCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**acceptCatalogPromptSuggestionsWithHttpInfo**](StoreIntegrationsApi.md#acceptCatalogPromptSuggestionsWithHttpInfo) | **POST** /catalog_prompt_suggestions/accept | Accept catalog prompt suggestions |
| [**createCatalogPromptSuggestions**](StoreIntegrationsApi.md#createCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**createCatalogPromptSuggestionsWithHttpInfo**](StoreIntegrationsApi.md#createCatalogPromptSuggestionsWithHttpInfo) | **POST** /catalog_prompt_suggestions | Suggest buyer prompts from catalog products |
| [**getStoreConnection**](StoreIntegrationsApi.md#getStoreConnection) | **GET** /store_connection | Match a store to a project |
| [**getStoreConnectionWithHttpInfo**](StoreIntegrationsApi.md#getStoreConnectionWithHttpInfo) | **GET** /store_connection | Match a store to a project |
| [**listAiOrders**](StoreIntegrationsApi.md#listAiOrders) | **GET** /ai_orders | Read AI-referred store orders |
| [**listAiOrdersWithHttpInfo**](StoreIntegrationsApi.md#listAiOrdersWithHttpInfo) | **GET** /ai_orders | Read AI-referred store orders |
| [**listCatalogPromptSuggestions**](StoreIntegrationsApi.md#listCatalogPromptSuggestions) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**listCatalogPromptSuggestionsWithHttpInfo**](StoreIntegrationsApi.md#listCatalogPromptSuggestionsWithHttpInfo) | **GET** /catalog_prompt_suggestions | List catalog prompt suggestions |
| [**rejectCatalogPromptSuggestions**](StoreIntegrationsApi.md#rejectCatalogPromptSuggestions) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**rejectCatalogPromptSuggestionsWithHttpInfo**](StoreIntegrationsApi.md#rejectCatalogPromptSuggestionsWithHttpInfo) | **POST** /catalog_prompt_suggestions/reject | Reject catalog prompt suggestions |
| [**replaceAiOrders**](StoreIntegrationsApi.md#replaceAiOrders) | **PUT** /ai_orders | Replace AI-referred store orders for a window |
| [**replaceAiOrdersWithHttpInfo**](StoreIntegrationsApi.md#replaceAiOrdersWithHttpInfo) | **PUT** /ai_orders | Replace AI-referred store orders for a window |



## acceptCatalogPromptSuggestions

> CatalogPromptSuggestionsAcceptResponse acceptCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionIdsRequest catalogPromptSuggestionIdsRequest = new CatalogPromptSuggestionIdsRequest(); // CatalogPromptSuggestionIdsRequest | 
        try {
            CatalogPromptSuggestionsAcceptResponse result = apiInstance.acceptCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#acceptCatalogPromptSuggestions");
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
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted and skipped suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## acceptCatalogPromptSuggestionsWithHttpInfo

> ApiResponse<CatalogPromptSuggestionsAcceptResponse> acceptCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionIdsRequest)

Accept catalog prompt suggestions

Starts tracking pending suggestions: each one becomes a prompt, tagged with a collection named after its product. Suggestions that are no longer pending come back in skipped. All accepted suggestions must share one country and language. When the new prompts would exceed the plan, the call returns ERR_LIMIT_REACHED and accepts nothing. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionIdsRequest catalogPromptSuggestionIdsRequest = new CatalogPromptSuggestionIdsRequest(); // CatalogPromptSuggestionIdsRequest | 
        try {
            ApiResponse<CatalogPromptSuggestionsAcceptResponse> response = apiInstance.acceptCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionIdsRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#acceptCatalogPromptSuggestions");
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
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

ApiResponse<[**CatalogPromptSuggestionsAcceptResponse**](CatalogPromptSuggestionsAcceptResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Accepted and skipped suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## createCatalogPromptSuggestions

> CatalogPromptSuggestionsCreateResponse createCatalogPromptSuggestions(catalogPromptSuggestionsCreateRequest)

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project&#39;s Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionsCreateRequest catalogPromptSuggestionsCreateRequest = new CatalogPromptSuggestionsCreateRequest(); // CatalogPromptSuggestionsCreateRequest | 
        try {
            CatalogPromptSuggestionsCreateResponse result = apiInstance.createCatalogPromptSuggestions(catalogPromptSuggestionsCreateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#createCatalogPromptSuggestions");
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
| **catalogPromptSuggestionsCreateRequest** | [**CatalogPromptSuggestionsCreateRequest**](CatalogPromptSuggestionsCreateRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The suggestions saved for these products |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **502** | The AI generation failed; retry the request |  -  |

## createCatalogPromptSuggestionsWithHttpInfo

> ApiResponse<CatalogPromptSuggestionsCreateResponse> createCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionsCreateRequest)

Suggest buyer prompts from catalog products

Writes buyer prompts for up to 20 catalog products and saves them as pending suggestions in the project&#39;s Suggested prompts queue, with the product recorded on each. Generation draws on the hourly prompt-suggestion allowance the app also uses (ERR_QUOTA_EXCEEDED once it is used up); a failed generation returns ERR_GENERATION_FAILED (502) and can be retried. Requires a &#x60;read_write&#x60; scope API key and, for team members, create access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionsCreateRequest catalogPromptSuggestionsCreateRequest = new CatalogPromptSuggestionsCreateRequest(); // CatalogPromptSuggestionsCreateRequest | 
        try {
            ApiResponse<CatalogPromptSuggestionsCreateResponse> response = apiInstance.createCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionsCreateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#createCatalogPromptSuggestions");
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
| **catalogPromptSuggestionsCreateRequest** | [**CatalogPromptSuggestionsCreateRequest**](CatalogPromptSuggestionsCreateRequest.md)|  | |

### Return type

ApiResponse<[**CatalogPromptSuggestionsCreateResponse**](CatalogPromptSuggestionsCreateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The suggestions saved for these products |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **502** | The AI generation failed; retry the request |  -  |


## getStoreConnection

> StoreConnectionResponse getStoreConnection(platform, domain)

Match a store to a project

Tells a store app whether the API key&#39;s account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        String platform = "shopify"; // String | Store platform
        String domain = "domain_example"; // String | Store domain, with or without scheme, e.g. acme-store.com
        try {
            StoreConnectionResponse result = apiInstance.getStoreConnection(platform, domain);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#getStoreConnection");
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
| **platform** | **String**| Store platform | [enum: shopify] |
| **domain** | **String**| Store domain, with or without scheme, e.g. acme-store.com | |

### Return type

[**StoreConnectionResponse**](StoreConnectionResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Eligibility, the matching project and the candidates |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **422** | Invalid parameters |  -  |

## getStoreConnectionWithHttpInfo

> ApiResponse<StoreConnectionResponse> getStoreConnectionWithHttpInfo(platform, domain)

Match a store to a project

Tells a store app whether the API key&#39;s account can use it and which project the store belongs to: the live project whose domain equals the store domain, else one whose domain is a parent or a subdomain of it, else null. candidates lists every live project of the account so the app can offer a picker. Takes no project_id. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        String platform = "shopify"; // String | Store platform
        String domain = "domain_example"; // String | Store domain, with or without scheme, e.g. acme-store.com
        try {
            ApiResponse<StoreConnectionResponse> response = apiInstance.getStoreConnectionWithHttpInfo(platform, domain);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#getStoreConnection");
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
| **platform** | **String**| Store platform | [enum: shopify] |
| **domain** | **String**| Store domain, with or without scheme, e.g. acme-store.com | |

### Return type

ApiResponse<[**StoreConnectionResponse**](StoreConnectionResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Eligibility, the matching project and the candidates |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **422** | Invalid parameters |  -  |


## listAiOrders

> AiOrdersResponse listAiOrders(projectId, platform, from, to)

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String platform = "shopify"; // String | Store platform
        LocalDate from = LocalDate.now(); // LocalDate | First day (YYYY-MM-DD). Defaults to 89 days before to
        LocalDate to = LocalDate.now(); // LocalDate | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days
        try {
            AiOrdersResponse result = apiInstance.listAiOrders(projectId, platform, from, to);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#listAiOrders");
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
| **platform** | **String**| Store platform | [optional] [default to shopify] [enum: shopify] |
| **from** | **LocalDate**| First day (YYYY-MM-DD). Defaults to 89 days before to | [optional] |
| **to** | **LocalDate**| Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [optional] |

### Return type

[**AiOrdersResponse**](AiOrdersResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Totals, per-assistant rows and the daily series |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## listAiOrdersWithHttpInfo

> ApiResponse<AiOrdersResponse> listAiOrdersWithHttpInfo(projectId, platform, from, to)

Read AI-referred store orders

Reads back the AI-referred orders a store app pushed for a project: totals, one row per AI assistant and a daily series of the days with orders. Revenue values are decimal strings in currency. Team members need read access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String platform = "shopify"; // String | Store platform
        LocalDate from = LocalDate.now(); // LocalDate | First day (YYYY-MM-DD). Defaults to 89 days before to
        LocalDate to = LocalDate.now(); // LocalDate | Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days
        try {
            ApiResponse<AiOrdersResponse> response = apiInstance.listAiOrdersWithHttpInfo(projectId, platform, from, to);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#listAiOrders");
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
| **platform** | **String**| Store platform | [optional] [default to shopify] [enum: shopify] |
| **from** | **LocalDate**| First day (YYYY-MM-DD). Defaults to 89 days before to | [optional] |
| **to** | **LocalDate**| Last day (YYYY-MM-DD). Defaults to today; the window is at most 400 days | [optional] |

### Return type

ApiResponse<[**AiOrdersResponse**](AiOrdersResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Totals, per-assistant rows and the daily series |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## listCatalogPromptSuggestions

> CatalogPromptSuggestionsResponse listCatalogPromptSuggestions(projectId, status, productExternalId, page, perPage)

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String status = "pending"; // String | Only suggestions in this status
        String productExternalId = "productExternalId_example"; // String | Only suggestions for this store product id
        Integer page = 1; // Integer | 
        Integer perPage = 50; // Integer | 
        try {
            CatalogPromptSuggestionsResponse result = apiInstance.listCatalogPromptSuggestions(projectId, status, productExternalId, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#listCatalogPromptSuggestions");
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
| **status** | **String**| Only suggestions in this status | [optional] [enum: pending, accepted, rejected] |
| **productExternalId** | **String**| Only suggestions for this store product id | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 50] |

### Return type

[**CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |

## listCatalogPromptSuggestionsWithHttpInfo

> ApiResponse<CatalogPromptSuggestionsResponse> listCatalogPromptSuggestionsWithHttpInfo(projectId, status, productExternalId, page, perPage)

List catalog prompt suggestions

Lists the buyer prompts suggested from a store catalog, oldest first, with their status and the product each one came from. Team members need read access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String status = "pending"; // String | Only suggestions in this status
        String productExternalId = "productExternalId_example"; // String | Only suggestions for this store product id
        Integer page = 1; // Integer | 
        Integer perPage = 50; // Integer | 
        try {
            ApiResponse<CatalogPromptSuggestionsResponse> response = apiInstance.listCatalogPromptSuggestionsWithHttpInfo(projectId, status, productExternalId, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#listCatalogPromptSuggestions");
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
| **status** | **String**| Only suggestions in this status | [optional] [enum: pending, accepted, rejected] |
| **productExternalId** | **String**| Only suggestions for this store product id | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 50] |

### Return type

ApiResponse<[**CatalogPromptSuggestionsResponse**](CatalogPromptSuggestionsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |


## rejectCatalogPromptSuggestions

> CatalogPromptSuggestionsRejectResponse rejectCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest)

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionIdsRequest catalogPromptSuggestionIdsRequest = new CatalogPromptSuggestionIdsRequest(); // CatalogPromptSuggestionIdsRequest | 
        try {
            CatalogPromptSuggestionsRejectResponse result = apiInstance.rejectCatalogPromptSuggestions(catalogPromptSuggestionIdsRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#rejectCatalogPromptSuggestions");
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
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

[**CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | How many suggestions were rejected |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## rejectCatalogPromptSuggestionsWithHttpInfo

> ApiResponse<CatalogPromptSuggestionsRejectResponse> rejectCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionIdsRequest)

Reject catalog prompt suggestions

Marks pending suggestions as rejected; suggestions that are no longer pending stay as they are. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to Prompts. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        CatalogPromptSuggestionIdsRequest catalogPromptSuggestionIdsRequest = new CatalogPromptSuggestionIdsRequest(); // CatalogPromptSuggestionIdsRequest | 
        try {
            ApiResponse<CatalogPromptSuggestionsRejectResponse> response = apiInstance.rejectCatalogPromptSuggestionsWithHttpInfo(catalogPromptSuggestionIdsRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#rejectCatalogPromptSuggestions");
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
| **catalogPromptSuggestionIdsRequest** | [**CatalogPromptSuggestionIdsRequest**](CatalogPromptSuggestionIdsRequest.md)|  | |

### Return type

ApiResponse<[**CatalogPromptSuggestionsRejectResponse**](CatalogPromptSuggestionsRejectResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | How many suggestions were rejected |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## replaceAiOrders

> AiOrdersUpdateResponse replaceAiOrders(aiOrdersUpdateRequest)

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order&#39;s first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        AiOrdersUpdateRequest aiOrdersUpdateRequest = new AiOrdersUpdateRequest(); // AiOrdersUpdateRequest | 
        try {
            AiOrdersUpdateResponse result = apiInstance.replaceAiOrders(aiOrdersUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#replaceAiOrders");
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
| **aiOrdersUpdateRequest** | [**AiOrdersUpdateRequest**](AiOrdersUpdateRequest.md)|  | |

### Return type

[**AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Rows stored and entries ignored |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## replaceAiOrdersWithHttpInfo

> ApiResponse<AiOrdersUpdateResponse> replaceAiOrdersWithHttpInfo(aiOrdersUpdateRequest)

Replace AI-referred store orders for a window

Replaces the daily AI-referred orders and revenue of the from..to window. Send the raw referring host or utm_source of each order&#39;s first visit as referrer: LLM Pulse classifies it and ignores anything that is not an AI assistant. Entries for the same day and assistant are summed. Every stored row of that project and platform inside the window is replaced, so pushing the same window again converges instead of counting twice. Rows are kept per project and platform, not per store, so one store reports per project. Requires a &#x60;read_write&#x60; scope API key and, for team members, update access to AI Traffic. Not available to accounts with a white-label portal or an embed (ERR_INTEGRATION_UNAVAILABLE).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.StoreIntegrationsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        StoreIntegrationsApi apiInstance = new StoreIntegrationsApi(defaultClient);
        AiOrdersUpdateRequest aiOrdersUpdateRequest = new AiOrdersUpdateRequest(); // AiOrdersUpdateRequest | 
        try {
            ApiResponse<AiOrdersUpdateResponse> response = apiInstance.replaceAiOrdersWithHttpInfo(aiOrdersUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling StoreIntegrationsApi#replaceAiOrders");
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
| **aiOrdersUpdateRequest** | [**AiOrdersUpdateRequest**](AiOrdersUpdateRequest.md)|  | |

### Return type

ApiResponse<[**AiOrdersUpdateResponse**](AiOrdersUpdateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Rows stored and entries ignored |  -  |
| **403** | The account has a white-label portal or an embed, so store integrations are not available (ERR_INTEGRATION_UNAVAILABLE). Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, and a team member without the permission ERR_INSUFFICIENT_PERMISSION, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

