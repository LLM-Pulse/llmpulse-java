# BingWebmasterToolsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getBingWebmasterPages**](BingWebmasterToolsApi.md#getBingWebmasterPages) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**getBingWebmasterPagesWithHttpInfo**](BingWebmasterToolsApi.md#getBingWebmasterPagesWithHttpInfo) | **GET** /bing_webmaster/pages | Top Bing Webmaster Tools pages (Growth+) |
| [**getBingWebmasterQueries**](BingWebmasterToolsApi.md#getBingWebmasterQueries) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**getBingWebmasterQueriesWithHttpInfo**](BingWebmasterToolsApi.md#getBingWebmasterQueriesWithHttpInfo) | **GET** /bing_webmaster/queries | Top Bing Webmaster Tools queries (Growth+) |
| [**getBingWebmasterSummary**](BingWebmasterToolsApi.md#getBingWebmasterSummary) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**getBingWebmasterSummaryWithHttpInfo**](BingWebmasterToolsApi.md#getBingWebmasterSummaryWithHttpInfo) | **GET** /bing_webmaster/summary | Bing Webmaster Tools summary (Growth+) |
| [**getBingWebmasterTimeseries**](BingWebmasterToolsApi.md#getBingWebmasterTimeseries) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |
| [**getBingWebmasterTimeseriesWithHttpInfo**](BingWebmasterToolsApi.md#getBingWebmasterTimeseriesWithHttpInfo) | **GET** /bing_webmaster/timeseries | Bing Webmaster Tools time series (Growth+) |



## getBingWebmasterPages

> BingWebmasterListResponse getBingWebmasterPages(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project&#39;s connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String sort = "impressions"; // String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            BingWebmasterListResponse result = apiInstance.getBingWebmasterPages(projectId, range, from, to, sort, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterPages");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top pages |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getBingWebmasterPagesWithHttpInfo

> ApiResponse<BingWebmasterListResponse> getBingWebmasterPagesWithHttpInfo(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools pages (Growth+)

The landing pages of the project&#39;s connected Bing Webmaster Tools site in Bing Search, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top pages of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String sort = "impressions"; // String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<BingWebmasterListResponse> response = apiInstance.getBingWebmasterPagesWithHttpInfo(projectId, range, from, to, sort, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterPages");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**BingWebmasterListResponse**](BingWebmasterListResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top pages |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## getBingWebmasterQueries

> BingWebmasterListResponse getBingWebmasterQueries(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project&#39;s connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String sort = "impressions"; // String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            BingWebmasterListResponse result = apiInstance.getBingWebmasterQueries(projectId, range, from, to, sort, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterQueries");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterListResponse**](BingWebmasterListResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top queries |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getBingWebmasterQueriesWithHttpInfo

> ApiResponse<BingWebmasterListResponse> getBingWebmasterQueriesWithHttpInfo(projectId, range, from, to, sort, page, perPage, output)

Top Bing Webmaster Tools queries (Growth+)

The Bing search queries of the project&#39;s connected Bing Webmaster Tools site, ranked and paginated. Each row sums the weekly figures Bing reports for the weeks whose week_ending (the Friday that closes a Bing week) falls in the window: clicks, impressions, ctr (a 0..1 fraction), avg_impression_position weighted by impressions and avg_click_position weighted by clicks (null without clicks). Bing reports only its top queries of each week, about 100, so the rows are not a complete set and never add up to /bing_webmaster/summary. weeks_covered counts the weeks found in the window and data_through is the last week_ending synced. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String sort = "impressions"; // String | Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last.
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<BingWebmasterListResponse> response = apiInstance.getBingWebmasterQueriesWithHttpInfo(projectId, range, from, to, sort, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterQueries");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **sort** | **String**| Sort key. impressions, clicks and ctr sort descending, the two positions ascending; rows without a value sort last. | [optional] [default to impressions] [enum: impressions, clicks, ctr, avg_impression_position, avg_click_position] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**BingWebmasterListResponse**](BingWebmasterListResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top queries |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## getBingWebmasterSummary

> BingWebmasterSummaryResponse getBingWebmasterSummary(projectId, range, from, to)

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences &gt; Project Settings &gt; Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        try {
            BingWebmasterSummaryResponse result = apiInstance.getBingWebmasterSummary(projectId, range, from, to);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterSummary");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |

### Return type

[**BingWebmasterSummaryResponse**](BingWebmasterSummaryResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools summary |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getBingWebmasterSummaryWithHttpInfo

> ApiResponse<BingWebmasterSummaryResponse> getBingWebmasterSummaryWithHttpInfo(projectId, range, from, to)

Bing Webmaster Tools summary (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site over a date range, summed from the daily site totals synced once a day. Bing reports no average position in its daily totals. About 13 months of history are kept; data_through is the last day synced, and later days are missing, not zero. history_current is false right after the site was changed in Preferences &gt; Project Settings &gt; Connections and before its first sync: the totals are then zero and data_through and last_synced_at null. A connection whose sync_status is on_hold (Bing refused the stored API key, or the site is no longer verified) still answers from the data already synced. Requires a connected Bing Webmaster Tools site and the Growth plan or above; otherwise returns ERR_BING_WEBMASTER_NOT_CONNECTED (with meta.connect_url) or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        try {
            ApiResponse<BingWebmasterSummaryResponse> response = apiInstance.getBingWebmasterSummaryWithHttpInfo(projectId, range, from, to);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterSummary");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |

### Return type

ApiResponse<[**BingWebmasterSummaryResponse**](BingWebmasterSummaryResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools summary |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## getBingWebmasterTimeseries

> BingWebmasterTimeseriesResponse getBingWebmasterTimeseries(projectId, range, from, to, granularity, output)

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String granularity = "day"; // String | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            BingWebmasterTimeseriesResponse result = apiInstance.getBingWebmasterTimeseries(projectId, range, from, to, granularity, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterTimeseries");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**BingWebmasterTimeseriesResponse**](BingWebmasterTimeseriesResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools time series |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getBingWebmasterTimeseriesWithHttpInfo

> ApiResponse<BingWebmasterTimeseriesResponse> getBingWebmasterTimeseriesWithHttpInfo(projectId, range, from, to, granularity, output)

Bing Webmaster Tools time series (Growth+)

Bing Search clicks, impressions and ctr (a 0..1 fraction) of the project&#39;s connected Bing Webmaster Tools site, bucketed by day, week (starting Monday) or month from the daily site totals synced once a day. Days without synced data are left out of the series, not reported as zero. Bing reports no average position in its daily totals. About 13 months of history are kept. history_current is false right after the site was changed and before its first sync: data is then empty. Requires a connected Bing Webmaster Tools site (ERR_BING_WEBMASTER_NOT_CONNECTED) and the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.BingWebmasterToolsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        BingWebmasterToolsApi apiInstance = new BingWebmasterToolsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to.
        LocalDate from = LocalDate.now(); // LocalDate | Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today.
        LocalDate to = LocalDate.now(); // LocalDate | End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches.
        String granularity = "day"; // String | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<BingWebmasterTimeseriesResponse> response = apiInstance.getBingWebmasterTimeseriesWithHttpInfo(projectId, range, from, to, granularity, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling BingWebmasterToolsApi#getBingWebmasterTimeseries");
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
| **range** | **Integer**| Number of days to look back, today included (alternative to from/to, which win when both are given). At most 487, the window the Search Console endpoints accept; about 13 months of Bing data are kept. A value that is not a plain positive number returns 422 ERR_INVALID_PARAM even beside from/to. | [optional] |
| **from** | **LocalDate**| Start date (YYYY-MM-DD). Without from and to, the window is the last 30 days, today included; with only to, from is 30 days before today. | [optional] |
| **to** | **LocalDate**| End date (YYYY-MM-DD), inclusive. Defaults to today. data_through in the response says how far the synced data reaches. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**BingWebmasterTimeseriesResponse**](BingWebmasterTimeseriesResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bing Webmaster Tools time series |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires the Growth plan or above |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

