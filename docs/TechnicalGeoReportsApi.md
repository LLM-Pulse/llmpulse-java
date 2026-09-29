# TechnicalGeoReportsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTechnicalGeoReports**](TechnicalGeoReportsApi.md#createTechnicalGeoReports) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**createTechnicalGeoReportsWithHttpInfo**](TechnicalGeoReportsApi.md#createTechnicalGeoReportsWithHttpInfo) | **POST** /technical_geo_reports | Run technical GEO analysis |
| [**getTechnicalGeoReport**](TechnicalGeoReportsApi.md#getTechnicalGeoReport) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**getTechnicalGeoReportWithHttpInfo**](TechnicalGeoReportsApi.md#getTechnicalGeoReportWithHttpInfo) | **GET** /technical_geo_reports/{id} | Get a technical GEO report |
| [**listTechnicalGeoReports**](TechnicalGeoReportsApi.md#listTechnicalGeoReports) | **GET** /technical_geo_reports | List technical GEO reports |
| [**listTechnicalGeoReportsWithHttpInfo**](TechnicalGeoReportsApi.md#listTechnicalGeoReportsWithHttpInfo) | **GET** /technical_geo_reports | List technical GEO reports |
| [**revertTechnicalGeoReportContent**](TechnicalGeoReportsApi.md#revertTechnicalGeoReportContent) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**revertTechnicalGeoReportContentWithHttpInfo**](TechnicalGeoReportsApi.md#revertTechnicalGeoReportContentWithHttpInfo) | **POST** /technical_geo_reports/{id}/revert_content | Revert llms.txt report content |
| [**updateTechnicalGeoReportContent**](TechnicalGeoReportsApi.md#updateTechnicalGeoReportContent) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |
| [**updateTechnicalGeoReportContentWithHttpInfo**](TechnicalGeoReportsApi.md#updateTechnicalGeoReportContentWithHttpInfo) | **PATCH** /technical_geo_reports/{id}/content | Edit llms.txt report content |



## createTechnicalGeoReports

> void createTechnicalGeoReports(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        CreateTechnicalGeoReportsRequest createTechnicalGeoReportsRequest = new CreateTechnicalGeoReportsRequest(); // CreateTechnicalGeoReportsRequest | 
        try {
            apiInstance.createTechnicalGeoReports(createTechnicalGeoReportsRequest);
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#createTechnicalGeoReports");
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
| **createTechnicalGeoReportsRequest** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md)|  | |

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
| **201** | Created. app_urls maps each created report type to the link that opens that report in the app |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

## createTechnicalGeoReportsWithHttpInfo

> ApiResponse<Void> createTechnicalGeoReportsWithHttpInfo(createTechnicalGeoReportsRequest)

Run technical GEO analysis

Launches the full nine-report technical GEO analysis bundle for a URL + country. The bundle starts only when at least nine daily units remain. Each successfully created report uses one unit; a report that is not created uses none. Daily allocations vary by account. Each report runs in a background job. Requires a &#x60;read_write&#x60; scope API key.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        CreateTechnicalGeoReportsRequest createTechnicalGeoReportsRequest = new CreateTechnicalGeoReportsRequest(); // CreateTechnicalGeoReportsRequest | 
        try {
            ApiResponse<Void> response = apiInstance.createTechnicalGeoReportsWithHttpInfo(createTechnicalGeoReportsRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#createTechnicalGeoReports");
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
| **createTechnicalGeoReportsRequest** | [**CreateTechnicalGeoReportsRequest**](CreateTechnicalGeoReportsRequest.md)|  | |

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
| **201** | Created. app_urls maps each created report type to the link that opens that report in the app |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |


## getTechnicalGeoReport

> void getTechnicalGeoReport(projectId, reportType, id)

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String reportType = "crawlability"; // String | 
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        try {
            apiInstance.getTechnicalGeoReport(projectId, reportType, id);
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#getTechnicalGeoReport");
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
| **reportType** | **String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |

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
| **200** | Report status and completed result data, plus app_url, the link that opens the report in the app |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getTechnicalGeoReportWithHttpInfo

> ApiResponse<Void> getTechnicalGeoReportWithHttpInfo(projectId, reportType, id)

Get a technical GEO report

Returns the current status and the full result_data once the report is completed. While it is running, result_data is null and poll_after_seconds tells clients when to check again. Summaries carry output_language_code (the ISO 639-1 code an llms_txt report was requested in; null for an llms_txt report written in the website&#39;s own language, requested as auto or chosen in the app, and for every other report type); a completed llms_txt result_data also returns content_version (send it back to PATCH /technical_geo_reports/{id}/content), manually_edited_at, original_llms_txt_content and original_llms_full_txt_content (the generated files, kept from the first manual edit in the app, the API or MCP) and metadata.output_language_code.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String reportType = "crawlability"; // String | 
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        try {
            ApiResponse<Void> response = apiInstance.getTechnicalGeoReportWithHttpInfo(projectId, reportType, id);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#getTechnicalGeoReport");
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
| **reportType** | **String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |

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
| **200** | Report status and completed result data, plus app_url, the link that opens the report in the app |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## listTechnicalGeoReports

> void listTechnicalGeoReports(projectId, reportType, status, batchId, page, perPage)

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String reportType = "crawlability"; // String | 
        String status = "status_example"; // String | Optional status filter; valid values depend on report_type
        Integer batchId = 56; // Integer | Optional batch id returned when the report bundle was created
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            apiInstance.listTechnicalGeoReports(projectId, reportType, status, batchId, page, perPage);
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#listTechnicalGeoReports");
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
| **reportType** | **String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **status** | **String**| Optional status filter; valid values depend on report_type | [optional] |
| **batchId** | **Integer**| Optional batch id returned when the report bundle was created | [optional] |
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
| **200** | Paginated technical GEO report summaries. Every summary carries app_url, the link that opens the report in the app |  -  |
| **422** | Invalid parameters |  -  |

## listTechnicalGeoReportsWithHttpInfo

> ApiResponse<Void> listTechnicalGeoReportsWithHttpInfo(projectId, reportType, status, batchId, page, perPage)

List technical GEO reports

Lists reports of one technical GEO type for a project, newest first. Use agent_readiness for the AI/Agent Readiness report.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String reportType = "crawlability"; // String | 
        String status = "status_example"; // String | Optional status filter; valid values depend on report_type
        Integer batchId = 56; // Integer | Optional batch id returned when the report bundle was created
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        try {
            ApiResponse<Void> response = apiInstance.listTechnicalGeoReportsWithHttpInfo(projectId, reportType, status, batchId, page, perPage);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#listTechnicalGeoReports");
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
| **reportType** | **String**|  | [enum: crawlability, schema, content_readiness, discoverability, site_structure, robots_txt, agent_readiness, llms_txt, ai_visibility] |
| **status** | **String**| Optional status filter; valid values depend on report_type | [optional] |
| **batchId** | **Integer**| Optional batch id returned when the report bundle was created | [optional] |
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
| **200** | Paginated technical GEO report summaries. Every summary carries app_url, the link that opens the report in the app |  -  |
| **422** | Invalid parameters |  -  |


## revertTechnicalGeoReportContent

> LlmsTxtTechnicalGeoReport revertTechnicalGeoReportContent(id, technicalGeoReportContentRevertRequest)

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        TechnicalGeoReportContentRevertRequest technicalGeoReportContentRevertRequest = new TechnicalGeoReportContentRevertRequest(); // TechnicalGeoReportContentRevertRequest | 
        try {
            LlmsTxtTechnicalGeoReport result = apiInstance.revertTechnicalGeoReportContent(id, technicalGeoReportContentRevertRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#revertTechnicalGeoReportContent");
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
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technicalGeoReportContentRevertRequest** | [**TechnicalGeoReportContentRevertRequest**](TechnicalGeoReportContentRevertRequest.md)|  | |

### Return type

[**LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its generated files restored |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## revertTechnicalGeoReportContentWithHttpInfo

> ApiResponse<LlmsTxtTechnicalGeoReport> revertTechnicalGeoReportContentWithHttpInfo(id, technicalGeoReportContentRevertRequest)

Revert llms.txt report content

Discards every manual edit on the llms_txt report and restores the llms.txt and llms-full.txt files exactly as they were generated. Returns ERR_INVALID_PARAM when the report has no manual edits or report_type is not llms_txt. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        TechnicalGeoReportContentRevertRequest technicalGeoReportContentRevertRequest = new TechnicalGeoReportContentRevertRequest(); // TechnicalGeoReportContentRevertRequest | 
        try {
            ApiResponse<LlmsTxtTechnicalGeoReport> response = apiInstance.revertTechnicalGeoReportContentWithHttpInfo(id, technicalGeoReportContentRevertRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#revertTechnicalGeoReportContent");
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
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technicalGeoReportContentRevertRequest** | [**TechnicalGeoReportContentRevertRequest**](TechnicalGeoReportContentRevertRequest.md)|  | |

### Return type

ApiResponse<[**LlmsTxtTechnicalGeoReport**](LlmsTxtTechnicalGeoReport.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its generated files restored |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## updateTechnicalGeoReportContent

> TechnicalGeoReportContentUpdateResponse updateTechnicalGeoReportContent(id, technicalGeoReportContentUpdateRequest)

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. &#x60;edits&#x60; maps llms_txt and/or llms_full_txt to the full replacement text. &#x60;content_version&#x60; must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty &#x60;edits&#x60; object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        TechnicalGeoReportContentUpdateRequest technicalGeoReportContentUpdateRequest = new TechnicalGeoReportContentUpdateRequest(); // TechnicalGeoReportContentUpdateRequest | 
        try {
            TechnicalGeoReportContentUpdateResponse result = apiInstance.updateTechnicalGeoReportContent(id, technicalGeoReportContentUpdateRequest);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#updateTechnicalGeoReportContent");
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
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technicalGeoReportContentUpdateRequest** | [**TechnicalGeoReportContentUpdateRequest**](TechnicalGeoReportContentUpdateRequest.md)|  | |

### Return type

[**TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its current files, plus the files that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## updateTechnicalGeoReportContentWithHttpInfo

> ApiResponse<TechnicalGeoReportContentUpdateResponse> updateTechnicalGeoReportContentWithHttpInfo(id, technicalGeoReportContentUpdateRequest)

Edit llms.txt report content

Replaces the llms.txt and llms-full.txt files of a completed llms_txt report in place, without generating them again. &#x60;edits&#x60; maps llms_txt and/or llms_full_txt to the full replacement text. &#x60;content_version&#x60; must equal result_data.content_version of the report as last read; when the report changed since, the edit is refused as stale and the message names the current version. A missing or stale content_version, a blank file, a file over 200,000 characters, a value that is not text, an unknown file key, an empty &#x60;edits&#x60; object, a report that has not completed or a report_type other than llms_txt is rejected with ERR_INVALID_PARAM and nothing is written. Files are stored with Unix line endings and one trailing newline. A file identical to the stored one is ignored, and the response lists the files that actually changed. The first edit keeps the generated files in original_llms_txt_content and original_llms_full_txt_content so POST /technical_geo_reports/{id}/revert_content can restore them; running the report again creates a new report without these edits. Requires a &#x60;read_write&#x60; scope API key and, for team members, create permission on GEO Optimization.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.TechnicalGeoReportsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        TechnicalGeoReportsApi apiInstance = new TechnicalGeoReportsApi(defaultClient);
        Integer id = 56; // Integer | Report id returned by POST /technical_geo_reports or GET /technical_geo_reports
        TechnicalGeoReportContentUpdateRequest technicalGeoReportContentUpdateRequest = new TechnicalGeoReportContentUpdateRequest(); // TechnicalGeoReportContentUpdateRequest | 
        try {
            ApiResponse<TechnicalGeoReportContentUpdateResponse> response = apiInstance.updateTechnicalGeoReportContentWithHttpInfo(id, technicalGeoReportContentUpdateRequest);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling TechnicalGeoReportsApi#updateTechnicalGeoReportContent");
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
| **id** | **Integer**| Report id returned by POST /technical_geo_reports or GET /technical_geo_reports | |
| **technicalGeoReportContentUpdateRequest** | [**TechnicalGeoReportContentUpdateRequest**](TechnicalGeoReportContentUpdateRequest.md)|  | |

### Return type

ApiResponse<[**TechnicalGeoReportContentUpdateResponse**](TechnicalGeoReportContentUpdateResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The report with its current files, plus the files that changed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

