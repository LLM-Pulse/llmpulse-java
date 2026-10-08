# GeoAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**compareGeoAuditRuns**](GeoAuditsApi.md#compareGeoAuditRuns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**compareGeoAuditRunsWithHttpInfo**](GeoAuditsApi.md#compareGeoAuditRunsWithHttpInfo) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**createGeoAudits**](GeoAuditsApi.md#createGeoAudits) | **POST** /geo_audits | Create GEO audits |
| [**createGeoAuditsWithHttpInfo**](GeoAuditsApi.md#createGeoAuditsWithHttpInfo) | **POST** /geo_audits | Create GEO audits |
| [**deleteGeoAudit**](GeoAuditsApi.md#deleteGeoAudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**deleteGeoAuditWithHttpInfo**](GeoAuditsApi.md#deleteGeoAuditWithHttpInfo) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**getGeoAudit**](GeoAuditsApi.md#getGeoAudit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**getGeoAuditWithHttpInfo**](GeoAuditsApi.md#getGeoAuditWithHttpInfo) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**getGeoAuditRun**](GeoAuditsApi.md#getGeoAuditRun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**getGeoAuditRunWithHttpInfo**](GeoAuditsApi.md#getGeoAuditRunWithHttpInfo) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**listGeoAlerts**](GeoAuditsApi.md#listGeoAlerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**listGeoAlertsWithHttpInfo**](GeoAuditsApi.md#listGeoAlertsWithHttpInfo) | **GET** /geo_alerts | List GEO audit alerts |
| [**listGeoAuditFindings**](GeoAuditsApi.md#listGeoAuditFindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**listGeoAuditFindingsWithHttpInfo**](GeoAuditsApi.md#listGeoAuditFindingsWithHttpInfo) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**listGeoAuditIssues**](GeoAuditsApi.md#listGeoAuditIssues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**listGeoAuditIssuesWithHttpInfo**](GeoAuditsApi.md#listGeoAuditIssuesWithHttpInfo) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**listGeoAuditRuns**](GeoAuditsApi.md#listGeoAuditRuns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**listGeoAuditRunsWithHttpInfo**](GeoAuditsApi.md#listGeoAuditRunsWithHttpInfo) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**listGeoAudits**](GeoAuditsApi.md#listGeoAudits) | **GET** /geo_audits | List GEO audits |
| [**listGeoAuditsWithHttpInfo**](GeoAuditsApi.md#listGeoAuditsWithHttpInfo) | **GET** /geo_audits | List GEO audits |
| [**runGeoAudit**](GeoAuditsApi.md#runGeoAudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**runGeoAuditWithHttpInfo**](GeoAuditsApi.md#runGeoAuditWithHttpInfo) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**updateGeoAudit**](GeoAuditsApi.md#updateGeoAudit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**updateGeoAuditWithHttpInfo**](GeoAuditsApi.md#updateGeoAuditWithHttpInfo) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**updateGeoAuditIssue**](GeoAuditsApi.md#updateGeoAuditIssue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |
| [**updateGeoAuditIssueWithHttpInfo**](GeoAuditsApi.md#updateGeoAuditIssueWithHttpInfo) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |



## compareGeoAuditRuns

> GeoAuditComparison compareGeoAuditRuns(projectId, id, fromRun, toRun)

Compare two GEO audit runs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        Integer fromRun = 56; // Integer | Run number to compare from (default the run before to_run)
        Integer toRun = 56; // Integer | Run number to compare to (default the latest completed run)
        try {
            GeoAuditComparison result = apiInstance.compareGeoAuditRuns(projectId, id, fromRun, toRun);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#compareGeoAuditRuns");
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
| **id** | **String**| Audit id | |
| **fromRun** | **Integer**| Run number to compare from (default the run before to_run) | [optional] |
| **toRun** | **Integer**| Run number to compare to (default the latest completed run) | [optional] |

### Return type

[**GeoAuditComparison**](GeoAuditComparison.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The comparison |  -  |
| **404** | Resource not found |  -  |

## compareGeoAuditRunsWithHttpInfo

> ApiResponse<GeoAuditComparison> compareGeoAuditRunsWithHttpInfo(projectId, id, fromRun, toRun)

Compare two GEO audit runs

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        Integer fromRun = 56; // Integer | Run number to compare from (default the run before to_run)
        Integer toRun = 56; // Integer | Run number to compare to (default the latest completed run)
        try {
            ApiResponse<GeoAuditComparison> response = apiInstance.compareGeoAuditRunsWithHttpInfo(projectId, id, fromRun, toRun);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#compareGeoAuditRuns");
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
| **id** | **String**| Audit id | |
| **fromRun** | **Integer**| Run number to compare from (default the run before to_run) | [optional] |
| **toRun** | **Integer**| Run number to compare to (default the latest completed run) | [optional] |

### Return type

ApiResponse<[**GeoAuditComparison**](GeoAuditComparison.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The comparison |  -  |
| **404** | Resource not found |  -  |


## createGeoAudits

> GeoAuditCreateResponse createGeoAudits(geoAuditCreateRequest)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        GeoAuditCreateRequest geoAuditCreateRequest = new GeoAuditCreateRequest(); // GeoAuditCreateRequest | 
        try {
            GeoAuditCreateResponse result = apiInstance.createGeoAudits(geoAuditCreateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#createGeoAudits");
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
| **geoAuditCreateRequest** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md)|  | |

### Return type

[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created audits |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

## createGeoAuditsWithHttpInfo

> ApiResponse<GeoAuditCreateResponse> createGeoAuditsWithHttpInfo(geoAuditCreateRequest)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        GeoAuditCreateRequest geoAuditCreateRequest = new GeoAuditCreateRequest(); // GeoAuditCreateRequest | 
        try {
            ApiResponse<GeoAuditCreateResponse> response = apiInstance.createGeoAuditsWithHttpInfo(geoAuditCreateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#createGeoAudits");
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
| **geoAuditCreateRequest** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md)|  | |

### Return type

ApiResponse<[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created audits |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |


## deleteGeoAudit

> GeoAuditArchived deleteGeoAudit(projectId, id)

Delete (archive) a GEO audit

Archives the audit. Requires a &#x60;read_write&#x60; scope API key and, for team members, delete permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        try {
            GeoAuditArchived result = apiInstance.deleteGeoAudit(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#deleteGeoAudit");
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
| **id** | **String**| Audit id | |

### Return type

[**GeoAuditArchived**](GeoAuditArchived.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Archived |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

## deleteGeoAuditWithHttpInfo

> ApiResponse<GeoAuditArchived> deleteGeoAuditWithHttpInfo(projectId, id)

Delete (archive) a GEO audit

Archives the audit. Requires a &#x60;read_write&#x60; scope API key and, for team members, delete permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        try {
            ApiResponse<GeoAuditArchived> response = apiInstance.deleteGeoAuditWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#deleteGeoAudit");
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
| **id** | **String**| Audit id | |

### Return type

ApiResponse<[**GeoAuditArchived**](GeoAuditArchived.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Archived |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |


## getGeoAudit

> GeoAuditResponse getGeoAudit(projectId, id)

Get a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        try {
            GeoAuditResponse result = apiInstance.getGeoAudit(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#getGeoAudit");
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
| **id** | **String**| Audit id | |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The audit |  -  |
| **404** | Resource not found |  -  |

## getGeoAuditWithHttpInfo

> ApiResponse<GeoAuditResponse> getGeoAuditWithHttpInfo(projectId, id)

Get a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String id = "id_example"; // String | Audit id
        try {
            ApiResponse<GeoAuditResponse> response = apiInstance.getGeoAuditWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#getGeoAudit");
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
| **id** | **String**| Audit id | |

### Return type

ApiResponse<[**GeoAuditResponse**](GeoAuditResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The audit |  -  |
| **404** | Resource not found |  -  |


## getGeoAuditRun

> GeoAuditRunDetail getGeoAuditRun(projectId, geoAuditId, sequence)

Get a GEO audit run

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer sequence = 56; // Integer | Run number within the audit
        try {
            GeoAuditRunDetail result = apiInstance.getGeoAuditRun(projectId, geoAuditId, sequence);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#getGeoAuditRun");
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
| **geoAuditId** | **String**| Audit id | |
| **sequence** | **Integer**| Run number within the audit | |

### Return type

[**GeoAuditRunDetail**](GeoAuditRunDetail.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The run with its result |  -  |
| **404** | Resource not found |  -  |

## getGeoAuditRunWithHttpInfo

> ApiResponse<GeoAuditRunDetail> getGeoAuditRunWithHttpInfo(projectId, geoAuditId, sequence)

Get a GEO audit run

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer sequence = 56; // Integer | Run number within the audit
        try {
            ApiResponse<GeoAuditRunDetail> response = apiInstance.getGeoAuditRunWithHttpInfo(projectId, geoAuditId, sequence);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#getGeoAuditRun");
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
| **geoAuditId** | **String**| Audit id | |
| **sequence** | **Integer**| Run number within the audit | |

### Return type

ApiResponse<[**GeoAuditRunDetail**](GeoAuditRunDetail.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The run with its result |  -  |
| **404** | Resource not found |  -  |


## listGeoAlerts

> GeoAlertList listGeoAlerts(projectId, auditId, page, perPage)

List GEO audit alerts

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String auditId = "auditId_example"; // String | Only alerts of this audit
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            GeoAlertList result = apiInstance.listGeoAlerts(projectId, auditId, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAlerts");
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
| **auditId** | **String**| Only alerts of this audit | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**GeoAlertList**](GeoAlertList.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated alerts |  -  |

## listGeoAlertsWithHttpInfo

> ApiResponse<GeoAlertList> listGeoAlertsWithHttpInfo(projectId, auditId, page, perPage)

List GEO audit alerts

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String auditId = "auditId_example"; // String | Only alerts of this audit
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<GeoAlertList> response = apiInstance.listGeoAlertsWithHttpInfo(projectId, auditId, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAlerts");
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
| **auditId** | **String**| Only alerts of this audit | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**GeoAlertList**](GeoAlertList.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated alerts |  -  |


## listGeoAuditFindings

> GeoAuditFindingList listGeoAuditFindings(projectId, geoAuditId, sequence, page, perPage, output)

List the findings of a GEO audit run

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer sequence = 56; // Integer | Run number within the audit
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            GeoAuditFindingList result = apiInstance.listGeoAuditFindings(projectId, geoAuditId, sequence, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditFindings");
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
| **geoAuditId** | **String**| Audit id | |
| **sequence** | **Integer**| Run number within the audit | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**GeoAuditFindingList**](GeoAuditFindingList.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated findings |  -  |
| **404** | Resource not found |  -  |

## listGeoAuditFindingsWithHttpInfo

> ApiResponse<GeoAuditFindingList> listGeoAuditFindingsWithHttpInfo(projectId, geoAuditId, sequence, page, perPage, output)

List the findings of a GEO audit run

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer sequence = 56; // Integer | Run number within the audit
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<GeoAuditFindingList> response = apiInstance.listGeoAuditFindingsWithHttpInfo(projectId, geoAuditId, sequence, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditFindings");
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
| **geoAuditId** | **String**| Audit id | |
| **sequence** | **Integer**| Run number within the audit | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**GeoAuditFindingList**](GeoAuditFindingList.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated findings |  -  |
| **404** | Resource not found |  -  |


## listGeoAuditIssues

> GeoAuditIssueList listGeoAuditIssues(projectId, geoAuditId, state, page, perPage)

List the issues of a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        String state = "open"; // String | open means open and not accepted; default all
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            GeoAuditIssueList result = apiInstance.listGeoAuditIssues(projectId, geoAuditId, state, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditIssues");
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
| **geoAuditId** | **String**| Audit id | |
| **state** | **String**| open means open and not accepted; default all | [optional] [enum: open, accepted, fixed, gone] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**GeoAuditIssueList**](GeoAuditIssueList.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated issues |  -  |
| **404** | Resource not found |  -  |

## listGeoAuditIssuesWithHttpInfo

> ApiResponse<GeoAuditIssueList> listGeoAuditIssuesWithHttpInfo(projectId, geoAuditId, state, page, perPage)

List the issues of a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        String state = "open"; // String | open means open and not accepted; default all
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<GeoAuditIssueList> response = apiInstance.listGeoAuditIssuesWithHttpInfo(projectId, geoAuditId, state, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditIssues");
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
| **geoAuditId** | **String**| Audit id | |
| **state** | **String**| open means open and not accepted; default all | [optional] [enum: open, accepted, fixed, gone] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**GeoAuditIssueList**](GeoAuditIssueList.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated issues |  -  |
| **404** | Resource not found |  -  |


## listGeoAuditRuns

> GeoAuditRunList listGeoAuditRuns(projectId, geoAuditId, page, perPage, output)

List the runs of a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            GeoAuditRunList result = apiInstance.listGeoAuditRuns(projectId, geoAuditId, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditRuns");
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
| **geoAuditId** | **String**| Audit id | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**GeoAuditRunList**](GeoAuditRunList.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated runs |  -  |
| **404** | Resource not found |  -  |

## listGeoAuditRunsWithHttpInfo

> ApiResponse<GeoAuditRunList> listGeoAuditRunsWithHttpInfo(projectId, geoAuditId, page, perPage, output)

List the runs of a GEO audit

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<GeoAuditRunList> response = apiInstance.listGeoAuditRunsWithHttpInfo(projectId, geoAuditId, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAuditRuns");
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
| **geoAuditId** | **String**| Audit id | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**GeoAuditRunList**](GeoAuditRunList.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated runs |  -  |
| **404** | Resource not found |  -  |


## listGeoAudits

> GeoAuditList listGeoAudits(projectId, auditType, status, cadence, page, perPage)

List GEO audits

Lists the project&#39;s audits, most recently updated first. Archived audits are left out unless status&#x3D;archived.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String auditType = "agent_readiness"; // String | 
        String status = "active"; // String | 
        String cadence = "once"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            GeoAuditList result = apiInstance.listGeoAudits(projectId, auditType, status, cadence, page, perPage);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAudits");
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
| **auditType** | **String**|  | [optional] [enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure] |
| **status** | **String**|  | [optional] [enum: active, paused, archived] |
| **cadence** | **String**|  | [optional] [enum: once, weekly, monthly] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

[**GeoAuditList**](GeoAuditList.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated audits |  -  |

## listGeoAuditsWithHttpInfo

> ApiResponse<GeoAuditList> listGeoAuditsWithHttpInfo(projectId, auditType, status, cadence, page, perPage)

List GEO audits

Lists the project&#39;s audits, most recently updated first. Archived audits are left out unless status&#x3D;archived.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String auditType = "agent_readiness"; // String | 
        String status = "active"; // String | 
        String cadence = "once"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<GeoAuditList> response = apiInstance.listGeoAuditsWithHttpInfo(projectId, auditType, status, cadence, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#listGeoAudits");
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
| **auditType** | **String**|  | [optional] [enum: agent_readiness, robots_txt, crawlability, schema, content_readiness, discoverability, site_structure] |
| **status** | **String**|  | [optional] [enum: active, paused, archived] |
| **cadence** | **String**|  | [optional] [enum: once, weekly, monthly] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |

### Return type

ApiResponse<[**GeoAuditList**](GeoAuditList.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated audits |  -  |


## runGeoAudit

> GeoAuditRunResponse runGeoAudit(projectId, geoAuditId)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        try {
            GeoAuditRunResponse result = apiInstance.runGeoAudit(projectId, geoAuditId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#runGeoAudit");
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
| **geoAuditId** | **String**| Audit id | |

### Return type

[**GeoAuditRunResponse**](GeoAuditRunResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The new run |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## runGeoAuditWithHttpInfo

> ApiResponse<GeoAuditRunResponse> runGeoAuditWithHttpInfo(projectId, geoAuditId)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        try {
            ApiResponse<GeoAuditRunResponse> response = apiInstance.runGeoAuditWithHttpInfo(projectId, geoAuditId);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#runGeoAudit");
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
| **geoAuditId** | **String**| Audit id | |

### Return type

ApiResponse<[**GeoAuditRunResponse**](GeoAuditRunResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The new run |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## updateGeoAudit

> GeoAuditResponse updateGeoAudit(id, geoAuditUpdateRequest)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        String id = "id_example"; // String | Audit id
        GeoAuditUpdateRequest geoAuditUpdateRequest = new GeoAuditUpdateRequest(); // GeoAuditUpdateRequest | 
        try {
            GeoAuditResponse result = apiInstance.updateGeoAudit(id, geoAuditUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#updateGeoAudit");
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
| **id** | **String**| Audit id | |
| **geoAuditUpdateRequest** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md)|  | |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated audit |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateGeoAuditWithHttpInfo

> ApiResponse<GeoAuditResponse> updateGeoAuditWithHttpInfo(id, geoAuditUpdateRequest)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        String id = "id_example"; // String | Audit id
        GeoAuditUpdateRequest geoAuditUpdateRequest = new GeoAuditUpdateRequest(); // GeoAuditUpdateRequest | 
        try {
            ApiResponse<GeoAuditResponse> response = apiInstance.updateGeoAuditWithHttpInfo(id, geoAuditUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#updateGeoAudit");
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
| **id** | **String**| Audit id | |
| **geoAuditUpdateRequest** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md)|  | |

### Return type

ApiResponse<[**GeoAuditResponse**](GeoAuditResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated audit |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## updateGeoAuditIssue

> GeoAuditIssueResponse updateGeoAuditIssue(geoAuditId, id, geoAuditIssueUpdateRequest)

Accept or reopen a GEO audit issue

Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer id = 56; // Integer | Issue id
        GeoAuditIssueUpdateRequest geoAuditIssueUpdateRequest = new GeoAuditIssueUpdateRequest(); // GeoAuditIssueUpdateRequest | 
        try {
            GeoAuditIssueResponse result = apiInstance.updateGeoAuditIssue(geoAuditId, id, geoAuditIssueUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#updateGeoAuditIssue");
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
| **geoAuditId** | **String**| Audit id | |
| **id** | **Integer**| Issue id | |
| **geoAuditIssueUpdateRequest** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md)|  | |

### Return type

[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated issue |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateGeoAuditIssueWithHttpInfo

> ApiResponse<GeoAuditIssueResponse> updateGeoAuditIssueWithHttpInfo(geoAuditId, id, geoAuditIssueUpdateRequest)

Accept or reopen a GEO audit issue

Requires a &#x60;read_write&#x60; scope API key and, for team members, update permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.GeoAuditsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        GeoAuditsApi apiInstance = new GeoAuditsApi(defaultClient);
        String geoAuditId = "geoAuditId_example"; // String | Audit id
        Integer id = 56; // Integer | Issue id
        GeoAuditIssueUpdateRequest geoAuditIssueUpdateRequest = new GeoAuditIssueUpdateRequest(); // GeoAuditIssueUpdateRequest | 
        try {
            ApiResponse<GeoAuditIssueResponse> response = apiInstance.updateGeoAuditIssueWithHttpInfo(geoAuditId, id, geoAuditIssueUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling GeoAuditsApi#updateGeoAuditIssue");
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
| **geoAuditId** | **String**| Audit id | |
| **id** | **Integer**| Issue id | |
| **geoAuditIssueUpdateRequest** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md)|  | |

### Return type

ApiResponse<[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated issue |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

