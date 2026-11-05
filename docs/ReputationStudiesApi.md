# ReputationStudiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createReputationReport**](ReputationStudiesApi.md#createReputationReport) | **POST** /reputation/reports | Start a reputation report |
| [**createReputationReportWithHttpInfo**](ReputationStudiesApi.md#createReputationReportWithHttpInfo) | **POST** /reputation/reports | Start a reputation report |
| [**getReputationReport**](ReputationStudiesApi.md#getReputationReport) | **GET** /reputation/reports/{id} | Get reputation report scores |
| [**getReputationReportWithHttpInfo**](ReputationStudiesApi.md#getReputationReportWithHttpInfo) | **GET** /reputation/reports/{id} | Get reputation report scores |
| [**getStudy**](ReputationStudiesApi.md#getStudy) | **GET** /studies/{id} | Get a custom AI study |
| [**getStudyWithHttpInfo**](ReputationStudiesApi.md#getStudyWithHttpInfo) | **GET** /studies/{id} | Get a custom AI study |
| [**getStudyReport**](ReputationStudiesApi.md#getStudyReport) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores |
| [**getStudyReportWithHttpInfo**](ReputationStudiesApi.md#getStudyReportWithHttpInfo) | **GET** /studies/{id}/reports/{report_id} | Get custom study report scores |
| [**listReputationReports**](ReputationStudiesApi.md#listReputationReports) | **GET** /reputation/reports | List reputation reports |
| [**listReputationReportsWithHttpInfo**](ReputationStudiesApi.md#listReputationReportsWithHttpInfo) | **GET** /reputation/reports | List reputation reports |
| [**listStudies**](ReputationStudiesApi.md#listStudies) | **GET** /studies | List custom AI studies |
| [**listStudiesWithHttpInfo**](ReputationStudiesApi.md#listStudiesWithHttpInfo) | **GET** /studies | List custom AI studies |



## createReputationReport

> ReputationReportCreateResponse createReputationReport(createReputationReportRequest)

Start a reputation report

Starts this month&#39;s Brand Reputation report, like the Generate button on the Reputation page: 201 with the new report (status pending). When the month already holds a report that did not fail, whether it is still running or finished, nothing new starts and the answer is 200 with created false and that report. With recalculate true it uses the month&#39;s one manual recalculation instead (the Recalculate This Month button): a fresh run across every analyst model, 201 when it starts, 200 with created false while a report is still running, and ERR_LIMIT_REACHED once the month holds two reports. Generation runs in the background: poll GET /reputation/reports until status is completed, then read the scores with GET /reputation/reports/{id}. ERR_RATE_LIMITED (429, with Retry-After) means another request is starting a report for the same project; retry after a few seconds. recalculate must be true or false and unknown fields are refused (ERR_INVALID_PARAM). Requires reputation monitoring on the account, a &#x60;read_write&#x60; scope API key and, for team members, create permission on Reputation.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        CreateReputationReportRequest createReputationReportRequest = new CreateReputationReportRequest(); // CreateReputationReportRequest | 
        try {
            ReputationReportCreateResponse result = apiInstance.createReputationReport(createReputationReportRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#createReputationReport");
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
| **createReputationReportRequest** | [**CreateReputationReportRequest**](CreateReputationReportRequest.md)|  | |

### Return type

[**ReputationReportCreateResponse**](ReputationReportCreateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Nothing new started; the report that already holds this month |  -  |
| **201** | The new report, status pending |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **429** | Another request is starting a report for this project; retry after a few seconds |  -  |

## createReputationReportWithHttpInfo

> ApiResponse<ReputationReportCreateResponse> createReputationReportWithHttpInfo(createReputationReportRequest)

Start a reputation report

Starts this month&#39;s Brand Reputation report, like the Generate button on the Reputation page: 201 with the new report (status pending). When the month already holds a report that did not fail, whether it is still running or finished, nothing new starts and the answer is 200 with created false and that report. With recalculate true it uses the month&#39;s one manual recalculation instead (the Recalculate This Month button): a fresh run across every analyst model, 201 when it starts, 200 with created false while a report is still running, and ERR_LIMIT_REACHED once the month holds two reports. Generation runs in the background: poll GET /reputation/reports until status is completed, then read the scores with GET /reputation/reports/{id}. ERR_RATE_LIMITED (429, with Retry-After) means another request is starting a report for the same project; retry after a few seconds. recalculate must be true or false and unknown fields are refused (ERR_INVALID_PARAM). Requires reputation monitoring on the account, a &#x60;read_write&#x60; scope API key and, for team members, create permission on Reputation.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        CreateReputationReportRequest createReputationReportRequest = new CreateReputationReportRequest(); // CreateReputationReportRequest | 
        try {
            ApiResponse<ReputationReportCreateResponse> response = apiInstance.createReputationReportWithHttpInfo(createReputationReportRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#createReputationReport");
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
| **createReputationReportRequest** | [**CreateReputationReportRequest**](CreateReputationReportRequest.md)|  | |

### Return type

ApiResponse<[**ReputationReportCreateResponse**](ReputationReportCreateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Nothing new started; the report that already holds this month |  -  |
| **201** | The new report, status pending |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |
| **429** | Another request is starting a report for this project; retry after a few seconds |  -  |


## getReputationReport

> void getReputationReport(id, projectId, page, perPage, model, brand, dimension, output)

Get reputation report scores

One reputation report&#39;s scores as flat rows: one row per analyst model, brand, dimension and attribute, with its 0-100 score and the reasoning the model gave. Scores come from several analyst models independently, so compare models rather than averaging them blindly.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        String id = "id_example"; // String | The report id from GET /reputation/reports
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Restrict to one analyst model
        String brand = "brand_example"; // String | Restrict to one brand name, or a comma-separated list
        String dimension = "dimension_example"; // String | Restrict to one reputation dimension key
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.getReputationReport(id, projectId, page, perPage, model, brand, dimension, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getReputationReport");
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
| **id** | **String**| The report id from GET /reputation/reports | |
| **projectId** | **Integer**| Project ID | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **brand** | **String**| Restrict to one brand name, or a comma-separated list | [optional] |
| **dimension** | **String**| Restrict to one reputation dimension key | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated score rows plus the report summary |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getReputationReportWithHttpInfo

> ApiResponse<Void> getReputationReportWithHttpInfo(id, projectId, page, perPage, model, brand, dimension, output)

Get reputation report scores

One reputation report&#39;s scores as flat rows: one row per analyst model, brand, dimension and attribute, with its 0-100 score and the reasoning the model gave. Scores come from several analyst models independently, so compare models rather than averaging them blindly.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        String id = "id_example"; // String | The report id from GET /reputation/reports
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Restrict to one analyst model
        String brand = "brand_example"; // String | Restrict to one brand name, or a comma-separated list
        String dimension = "dimension_example"; // String | Restrict to one reputation dimension key
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.getReputationReportWithHttpInfo(id, projectId, page, perPage, model, brand, dimension, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getReputationReport");
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
| **id** | **String**| The report id from GET /reputation/reports | |
| **projectId** | **Integer**| Project ID | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **brand** | **String**| Restrict to one brand name, or a comma-separated list | [optional] |
| **dimension** | **String**| Restrict to one reputation dimension key | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated score rows plus the report summary |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## getStudy

> void getStudy(id)

Get a custom AI study

One study with its brief, the subjects it compares, the dimensions it scores them on, and its report history. Use the ids in &#x60;reports&#x60; with GET /studies/{id}/reports/{report_id}.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer id = 56; // Integer | 
        try {
            apiInstance.getStudy(id);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getStudy");
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
| **200** | The study |  -  |
| **404** | Resource not found |  -  |

## getStudyWithHttpInfo

> ApiResponse<Void> getStudyWithHttpInfo(id)

Get a custom AI study

One study with its brief, the subjects it compares, the dimensions it scores them on, and its report history. Use the ids in &#x60;reports&#x60; with GET /studies/{id}/reports/{report_id}.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer id = 56; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.getStudyWithHttpInfo(id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getStudy");
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
| **200** | The study |  -  |
| **404** | Resource not found |  -  |


## getStudyReport

> void getStudyReport(id, reportId, page, perPage, model, subject, dimension, output)

Get custom study report scores

One custom-study report&#39;s scores as flat rows: one row per analyst model, subject, dimension and attribute, with its 0-100 score and the reasoning the model gave.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer id = 56; // Integer | 
        String reportId = "reportId_example"; // String | The report id from GET /studies/{id}
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Restrict to one analyst model
        String subject = "subject_example"; // String | Restrict to one subject name, or a comma-separated list
        String dimension = "dimension_example"; // String | Restrict to one dimension key
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.getStudyReport(id, reportId, page, perPage, model, subject, dimension, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getStudyReport");
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
| **reportId** | **String**| The report id from GET /studies/{id} | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **subject** | **String**| Restrict to one subject name, or a comma-separated list | [optional] |
| **dimension** | **String**| Restrict to one dimension key | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated score rows plus the report summary |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getStudyReportWithHttpInfo

> ApiResponse<Void> getStudyReportWithHttpInfo(id, reportId, page, perPage, model, subject, dimension, output)

Get custom study report scores

One custom-study report&#39;s scores as flat rows: one row per analyst model, subject, dimension and attribute, with its 0-100 score and the reasoning the model gave.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer id = 56; // Integer | 
        String reportId = "reportId_example"; // String | The report id from GET /studies/{id}
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String model = "chatgpt"; // String | Restrict to one analyst model
        String subject = "subject_example"; // String | Restrict to one subject name, or a comma-separated list
        String dimension = "dimension_example"; // String | Restrict to one dimension key
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.getStudyReportWithHttpInfo(id, reportId, page, perPage, model, subject, dimension, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#getStudyReport");
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
| **reportId** | **String**| The report id from GET /studies/{id} | |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **model** | **String**| Restrict to one analyst model | [optional] [enum: chatgpt, perplexity, gemini, deepseek, grok, claude] |
| **subject** | **String**| Restrict to one subject name, or a comma-separated list | [optional] |
| **dimension** | **String**| Restrict to one dimension key | [optional] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated score rows plus the report summary |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## listReputationReports

> void listReputationReports(projectId, page, perPage, output)

List reputation reports

The monthly multi-model analyst reports scoring the tracked brand and its competitors, newest first. Pending and failed reports are included on purpose: whether this month ran at all is often the question. Each row carries the report id, its status, and which analyst models produced data. Requires reputation monitoring to be enabled on the account.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listReputationReports(projectId, page, perPage, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#listReputationReports");
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


null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated report summaries |  -  |

## listReputationReportsWithHttpInfo

> ApiResponse<Void> listReputationReportsWithHttpInfo(projectId, page, perPage, output)

List reputation reports

The monthly multi-model analyst reports scoring the tracked brand and its competitors, newest first. Pending and failed reports are included on purpose: whether this month ran at all is often the question. Each row carries the report id, its status, and which analyst models produced data. Requires reputation monitoring to be enabled on the account.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listReputationReportsWithHttpInfo(projectId, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#listReputationReports");
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


ApiResponse<Void>

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated report summaries |  -  |


## listStudies

> void listStudies(projectId, status, page, perPage, output)

List custom AI studies

The custom AI studies defined on the account: analyst reports over any set of subjects (brands, sectors, topics) and any set of dimensions. Studies belong to the ACCOUNT, not to a project, so project_id is an optional filter here and account-level studies are returned whichever project you filter by. A team member whose project access is restricted sees only the studies of the projects they can reach. Requires reputation monitoring to be enabled on the account.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer projectId = 56; // Integer | Restrict to studies attached to this project (plus account-level ones)
        String status = "active"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listStudies(projectId, status, page, perPage, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#listStudies");
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
| **projectId** | **Integer**| Restrict to studies attached to this project (plus account-level ones) | [optional] |
| **status** | **String**|  | [optional] [enum: active, archived] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated study summaries |  -  |

## listStudiesWithHttpInfo

> ApiResponse<Void> listStudiesWithHttpInfo(projectId, status, page, perPage, output)

List custom AI studies

The custom AI studies defined on the account: analyst reports over any set of subjects (brands, sectors, topics) and any set of dimensions. Studies belong to the ACCOUNT, not to a project, so project_id is an optional filter here and account-level studies are returned whichever project you filter by. A team member whose project access is restricted sees only the studies of the projects they can reach. Requires reputation monitoring to be enabled on the account.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ReputationStudiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ReputationStudiesApi apiInstance = new ReputationStudiesApi(defaultClient);
        Integer projectId = 56; // Integer | Restrict to studies attached to this project (plus account-level ones)
        String status = "active"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listStudiesWithHttpInfo(projectId, status, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ReputationStudiesApi#listStudies");
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
| **projectId** | **Integer**| Restrict to studies attached to this project (plus account-level ones) | [optional] |
| **status** | **String**|  | [optional] [enum: active, archived] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

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
| **200** | Paginated study summaries |  -  |

