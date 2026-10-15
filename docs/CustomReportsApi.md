# CustomReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getCustomReport**](CustomReportsApi.md#getCustomReport) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**getCustomReportWithHttpInfo**](CustomReportsApi.md#getCustomReportWithHttpInfo) | **GET** /custom_reports/{id} | Get a custom report with its widget data |
| [**listCustomReports**](CustomReportsApi.md#listCustomReports) | **GET** /custom_reports | List custom reports |
| [**listCustomReportsWithHttpInfo**](CustomReportsApi.md#listCustomReportsWithHttpInfo) | **GET** /custom_reports | List custom reports |
| [**sendCustomReport**](CustomReportsApi.md#sendCustomReport) | **POST** /custom_reports/{id}/send | Send a custom report now |
| [**sendCustomReportWithHttpInfo**](CustomReportsApi.md#sendCustomReportWithHttpInfo) | **POST** /custom_reports/{id}/send | Send a custom report now |



## getCustomReport

> CustomReportDetailResponse getCustomReport(projectId, id)

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its &#x60;kind&#x60; and a &#x60;data&#x60; object shaped by it: &#x60;series&#x60; for &#x60;timeseries&#x60;, &#x60;slices&#x60; for &#x60;donut&#x60;, &#x60;bars&#x60; for &#x60;bar&#x60;, &#x60;values&#x60; and &#x60;changes&#x60; for &#x60;kpi_grid&#x60;, &#x60;rows&#x60; for &#x60;table&#x60;. A widget whose data source is not connected has &#x60;available: false&#x60; and &#x60;data: null&#x60;. Nothing is saved or sent. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | Custom report id, from GET /custom_reports
        try {
            CustomReportDetailResponse result = apiInstance.getCustomReport(projectId, id);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#getCustomReport");
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
| **id** | **Integer**| Custom report id, from GET /custom_reports | |

### Return type

[**CustomReportDetailResponse**](CustomReportDetailResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Report configuration and widget data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

## getCustomReportWithHttpInfo

> ApiResponse<CustomReportDetailResponse> getCustomReportWithHttpInfo(projectId, id)

Get a custom report with its widget data

The configuration of one custom report (date range, filters, schedule, layout) and the data of every widget computed for today, the same numbers the report page, its shared link and its PDF show. Each widget carries its &#x60;kind&#x60; and a &#x60;data&#x60; object shaped by it: &#x60;series&#x60; for &#x60;timeseries&#x60;, &#x60;slices&#x60; for &#x60;donut&#x60;, &#x60;bars&#x60; for &#x60;bar&#x60;, &#x60;values&#x60; and &#x60;changes&#x60; for &#x60;kpi_grid&#x60;, &#x60;rows&#x60; for &#x60;table&#x60;. A widget whose data source is not connected has &#x60;available: false&#x60; and &#x60;data: null&#x60;. Nothing is saved or sent. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer id = 56; // Integer | Custom report id, from GET /custom_reports
        try {
            ApiResponse<CustomReportDetailResponse> response = apiInstance.getCustomReportWithHttpInfo(projectId, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#getCustomReport");
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
| **id** | **Integer**| Custom report id, from GET /custom_reports | |

### Return type

ApiResponse<[**CustomReportDetailResponse**](CustomReportDetailResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Report configuration and widget data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |


## listCustomReports

> CustomReportsResponse listCustomReports(projectId, page, perPage, output)

List custom reports

The custom reports of the project, newest first, as the Reports &gt; Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            CustomReportsResponse result = apiInstance.listCustomReports(projectId, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#listCustomReports");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**CustomReportsResponse**](CustomReportsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated custom reports |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

## listCustomReportsWithHttpInfo

> ApiResponse<CustomReportsResponse> listCustomReportsWithHttpInfo(projectId, page, perPage, output)

List custom reports

The custom reports of the project, newest first, as the Reports &gt; Custom Reports list shows them. Recipient addresses, the shared-link token and the password are never returned. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<CustomReportsResponse> response = apiInstance.listCustomReportsWithHttpInfo(projectId, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#listCustomReports");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**CustomReportsResponse**](CustomReportsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated custom reports |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |


## sendCustomReport

> CustomReportSendResponse sendCustomReport(id, sendCustomReportRequest)

Send a custom report now

Queues the report&#39;s PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a &#x60;read_write&#x60; scope API key and, for team members, update permission on Custom Reports.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer id = 56; // Integer | Custom report id, from GET /custom_reports
        SendCustomReportRequest sendCustomReportRequest = new SendCustomReportRequest(); // SendCustomReportRequest | 
        try {
            CustomReportSendResponse result = apiInstance.sendCustomReport(id, sendCustomReportRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#sendCustomReport");
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
| **id** | **Integer**| Custom report id, from GET /custom_reports | |
| **sendCustomReportRequest** | [**SendCustomReportRequest**](SendCustomReportRequest.md)|  | |

### Return type

[**CustomReportSendResponse**](CustomReportSendResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The report is queued for its recipients |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, a team member without the permission ERR_INSUFFICIENT_PERMISSION, and a request made on a white-label portal host, where the app does not offer this action, ERR_INTEGRATION_UNAVAILABLE, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **429** | The report was sent less than 10 minutes ago; retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

## sendCustomReportWithHttpInfo

> ApiResponse<CustomReportSendResponse> sendCustomReportWithHttpInfo(id, sendCustomReportRequest)

Send a custom report now

Queues the report&#39;s PDF for its recipients, like the Send now button on the report page: the report must be published and have at least one recipient (ERR_INVALID_PARAM otherwise), and each report can be sent once every 10 minutes (429 ERR_RATE_LIMITED with Retry-After). Not available from a white-label portal or for a report made inside one (ERR_INTEGRATION_UNAVAILABLE). Requires the Scale plan or above, a &#x60;read_write&#x60; scope API key and, for team members, update permission on Custom Reports.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.CustomReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        CustomReportsApi apiInstance = new CustomReportsApi(defaultClient);
        Integer id = 56; // Integer | Custom report id, from GET /custom_reports
        SendCustomReportRequest sendCustomReportRequest = new SendCustomReportRequest(); // SendCustomReportRequest | 
        try {
            ApiResponse<CustomReportSendResponse> response = apiInstance.sendCustomReportWithHttpInfo(id, sendCustomReportRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling CustomReportsApi#sendCustomReport");
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
| **id** | **Integer**| Custom report id, from GET /custom_reports | |
| **sendCustomReportRequest** | [**SendCustomReportRequest**](SendCustomReportRequest.md)|  | |

### Return type

ApiResponse<[**CustomReportSendResponse**](CustomReportSendResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | The report is queued for its recipients |  -  |
| **403** | Writes with a read-only key answer ERR_INSUFFICIENT_SCOPE, a team member without the permission ERR_INSUFFICIENT_PERMISSION, and a request made on a white-label portal host, where the app does not offer this action, ERR_INTEGRATION_UNAVAILABLE, with the same status |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **429** | The report was sent less than 10 minutes ago; retry after the number of seconds in the Retry-After header |  * Retry-After - Seconds until the report can be sent again <br>  |

