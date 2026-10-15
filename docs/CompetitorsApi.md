# CompetitorsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCompetitor**](CompetitorsApi.md#createCompetitor) | **POST** /competitors | Add a competitor |
| [**createCompetitorWithHttpInfo**](CompetitorsApi.md#createCompetitorWithHttpInfo) | **POST** /competitors | Add a competitor |
| [**deleteCompetitor**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /competitors/{id} | Delete a competitor |
| [**deleteCompetitorWithHttpInfo**](CompetitorsApi.md#deleteCompetitorWithHttpInfo) | **DELETE** /competitors/{id} | Delete a competitor |
| [**getCompetitorDetails**](CompetitorsApi.md#getCompetitorDetails) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**getCompetitorDetailsWithHttpInfo**](CompetitorsApi.md#getCompetitorDetailsWithHttpInfo) | **GET** /dimensions/competitors/{id} | Competitor details |
| [**listCompetitorSuggestions**](CompetitorsApi.md#listCompetitorSuggestions) | **GET** /competitors/suggestions | List competitor suggestions |
| [**listCompetitorSuggestionsWithHttpInfo**](CompetitorsApi.md#listCompetitorSuggestionsWithHttpInfo) | **GET** /competitors/suggestions | List competitor suggestions |
| [**listCompetitors**](CompetitorsApi.md#listCompetitors) | **GET** /dimensions/competitors | List competitors |
| [**listCompetitorsWithHttpInfo**](CompetitorsApi.md#listCompetitorsWithHttpInfo) | **GET** /dimensions/competitors | List competitors |
| [**updateCompetitor**](CompetitorsApi.md#updateCompetitor) | **PATCH** /competitors/{id} | Update a competitor |
| [**updateCompetitorWithHttpInfo**](CompetitorsApi.md#updateCompetitorWithHttpInfo) | **PATCH** /competitors/{id} | Update a competitor |



## createCompetitor

> CompetitorCreateResponse createCompetitor(createCompetitorRequest)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        CreateCompetitorRequest createCompetitorRequest = new CreateCompetitorRequest(); // CreateCompetitorRequest | 
        try {
            CompetitorCreateResponse result = apiInstance.createCompetitor(createCompetitorRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#createCompetitor");
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
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md)|  | |

### Return type

[**CompetitorCreateResponse**](CompetitorCreateResponse.md)


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

## createCompetitorWithHttpInfo

> ApiResponse<CompetitorCreateResponse> createCompetitorWithHttpInfo(createCompetitorRequest)

Add a competitor

Adds a competitor with its own citation URL matching rule. Honours the per-plan max competitors cap. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        CreateCompetitorRequest createCompetitorRequest = new CreateCompetitorRequest(); // CreateCompetitorRequest | 
        try {
            ApiResponse<CompetitorCreateResponse> response = apiInstance.createCompetitorWithHttpInfo(createCompetitorRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#createCompetitor");
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
| **createCompetitorRequest** | [**CreateCompetitorRequest**](CreateCompetitorRequest.md)|  | |

### Return type

ApiResponse<[**CompetitorCreateResponse**](CompetitorCreateResponse.md)>


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


## deleteCompetitor

> void deleteCompetitor(projectId, id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            apiInstance.deleteCompetitor(projectId, id);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#deleteCompetitor");
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


null (empty response body)

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

## deleteCompetitorWithHttpInfo

> ApiResponse<Void> deleteCompetitorWithHttpInfo(projectId, id)

Delete a competitor

Deletes a competitor (irreversible). It disappears immediately and frees a competitor slot; a background job then deletes its mentions, citations, sentiment and share of voice history. Its ads, shopping products, local businesses and brand entities are kept and move to the project or another competitor they match, or stay unattributed. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.deleteCompetitorWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#deleteCompetitor");
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


ApiResponse<Void>

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


## getCompetitorDetails

> CompetitorDetails getCompetitorDetails(projectId, id)

Competitor details

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            CompetitorDetails result = apiInstance.getCompetitorDetails(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#getCompetitorDetails");
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

[**CompetitorDetails**](CompetitorDetails.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitor details |  -  |

## getCompetitorDetailsWithHttpInfo

> ApiResponse<CompetitorDetails> getCompetitorDetailsWithHttpInfo(projectId, id)

Competitor details

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | 
        try {
            ApiResponse<CompetitorDetails> response = apiInstance.getCompetitorDetailsWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#getCompetitorDetails");
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

ApiResponse<[**CompetitorDetails**](CompetitorDetails.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitor details |  -  |


## listCompetitorSuggestions

> CompetitorSuggestionsResponse listCompetitorSuggestions(projectId, basis, query, page, perPage, output)

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. &#x60;basis&#x3D;brands&#x60; (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (&#x60;mentions&#x60;). &#x60;basis&#x3D;citations&#x60; returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (&#x60;citations&#x60;). &#x60;discovery&#x60; tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String basis = "brands"; // String | 
        String query = "query_example"; // String | Only suggestions whose brand name or domain contains this text
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            CompetitorSuggestionsResponse result = apiInstance.listCompetitorSuggestions(projectId, basis, query, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#listCompetitorSuggestions");
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
| **basis** | **String**|  | [optional] [default to brands] [enum: brands, citations] |
| **query** | **String**| Only suggestions whose brand name or domain contains this text | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**CompetitorSuggestionsResponse**](CompetitorSuggestionsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **422** | Invalid parameters |  -  |

## listCompetitorSuggestionsWithHttpInfo

> ApiResponse<CompetitorSuggestionsResponse> listCompetitorSuggestionsWithHttpInfo(projectId, basis, query, page, perPage, output)

List competitor suggestions

The two lists of the Suggested tab of the Competitors page. &#x60;basis&#x3D;brands&#x60; (default) returns the competing brands the AI discovery proposed that are not tracked or rejected yet, with the names it would match and, when counted, how many answers name it (&#x60;mentions&#x60;). &#x60;basis&#x3D;citations&#x60; returns the domains AI answers cite most that are not your own or tracked yet, with how many answers cite each (&#x60;citations&#x60;). &#x60;discovery&#x60; tells whether a discovery run is still loading. Read-only: it never starts a discovery run, which the page starts from its Discover button. Add a suggestion with POST /competitors.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String basis = "brands"; // String | 
        String query = "query_example"; // String | Only suggestions whose brand name or domain contains this text
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<CompetitorSuggestionsResponse> response = apiInstance.listCompetitorSuggestionsWithHttpInfo(projectId, basis, query, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#listCompetitorSuggestions");
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
| **basis** | **String**|  | [optional] [default to brands] [enum: brands, citations] |
| **query** | **String**| Only suggestions whose brand name or domain contains this text | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**CompetitorSuggestionsResponse**](CompetitorSuggestionsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated suggestions |  -  |
| **422** | Invalid parameters |  -  |


## listCompetitors

> ListCompetitors200Response listCompetitors(projectId, includeProjectBrand, output)

List competitors

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Boolean includeProjectBrand = false; // Boolean | When true, prepends the project brand with actor_type=project and is_own=true
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ListCompetitors200Response result = apiInstance.listCompetitors(projectId, includeProjectBrand, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#listCompetitors");
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
| **includeProjectBrand** | **Boolean**| When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional] [default to false] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**ListCompetitors200Response**](ListCompetitors200Response.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitors |  -  |

## listCompetitorsWithHttpInfo

> ApiResponse<ListCompetitors200Response> listCompetitorsWithHttpInfo(projectId, includeProjectBrand, output)

List competitors

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Boolean includeProjectBrand = false; // Boolean | When true, prepends the project brand with actor_type=project and is_own=true
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<ListCompetitors200Response> response = apiInstance.listCompetitorsWithHttpInfo(projectId, includeProjectBrand, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#listCompetitors");
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
| **includeProjectBrand** | **Boolean**| When true, prepends the project brand with actor_type&#x3D;project and is_own&#x3D;true | [optional] [default to false] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**ListCompetitors200Response**](ListCompetitors200Response.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Competitors |  -  |


## updateCompetitor

> void updateCompetitor(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer id = 56; // Integer | 
        UpdateCompetitorRequest updateCompetitorRequest = new UpdateCompetitorRequest(); // UpdateCompetitorRequest | 
        try {
            apiInstance.updateCompetitor(id, updateCompetitorRequest);
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#updateCompetitor");
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
| **updateCompetitorRequest** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md)|  | |

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
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateCompetitorWithHttpInfo

> ApiResponse<Void> updateCompetitorWithHttpInfo(id, updateCompetitorRequest)

Update a competitor

Updates brand_name, the competitor website domain or host, matching_names (full replacement list; the brand name is always included automatically), color and/or the citation URL matching rule. Website domain/host and citation-rule changes share one seven-day cooldown per competitor; other fields remain editable during the cooldown. Name, website or citation-rule changes re-run historical matching in the background: the competitor shows processing&#x3D;true for a few minutes and further edits are rejected meanwhile. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CompetitorsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CompetitorsApi apiInstance = new CompetitorsApi(defaultClient);
        Integer id = 56; // Integer | 
        UpdateCompetitorRequest updateCompetitorRequest = new UpdateCompetitorRequest(); // UpdateCompetitorRequest | 
        try {
            ApiResponse<Void> response = apiInstance.updateCompetitorWithHttpInfo(id, updateCompetitorRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling CompetitorsApi#updateCompetitor");
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
| **updateCompetitorRequest** | [**UpdateCompetitorRequest**](UpdateCompetitorRequest.md)|  | |

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
| **200** | Updated |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

