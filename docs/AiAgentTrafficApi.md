# AiAgentTrafficApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAgentTraffic**](AiAgentTrafficApi.md#getAgentTraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**getAgentTrafficWithHttpInfo**](AiAgentTrafficApi.md#getAgentTrafficWithHttpInfo) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale plan or above, Beta) |
| [**getAiTraffic**](AiAgentTrafficApi.md#getAiTraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**getAiTrafficWithHttpInfo**](AiAgentTrafficApi.md#getAiTrafficWithHttpInfo) | **GET** /metrics/ai_traffic | AI referral traffic (Scale plan or above) |
| [**listAgentBots**](AiAgentTrafficApi.md#listAgentBots) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |
| [**listAgentBotsWithHttpInfo**](AiAgentTrafficApi.md#listAgentBotsWithHttpInfo) | **GET** /dimensions/agent_bots | AI bot catalog (Scale plan or above) |



## getAgentTraffic

> AgentTrafficResponse getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project&#39;s origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String bot = "bot_example"; // String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
        String company = "company_example"; // String | Filter by company (e.g. openai, anthropic, google)
        String groupBy = "bot"; // String | 
        String granularity = "day"; // String | 
        try {
            AgentTrafficResponse result = apiInstance.getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#getAgentTraffic");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **bot** | **String**| Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional] |
| **company** | **String**| Filter by company (e.g. openai, anthropic, google) | [optional] |
| **groupBy** | **String**|  | [optional] [default to bot] [enum: bot, company] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |

### Return type

[**AgentTrafficResponse**](AgentTrafficResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

## getAgentTrafficWithHttpInfo

> ApiResponse<AgentTrafficResponse> getAgentTrafficWithHttpInfo(projectId, range, from, to, bot, company, groupBy, granularity)

AI bot crawler traffic (Scale plan or above, Beta)

Aggregated AI bot traffic hitting the project&#39;s origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String bot = "bot_example"; // String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
        String company = "company_example"; // String | Filter by company (e.g. openai, anthropic, google)
        String groupBy = "bot"; // String | 
        String granularity = "day"; // String | 
        try {
            ApiResponse<AgentTrafficResponse> response = apiInstance.getAgentTrafficWithHttpInfo(projectId, range, from, to, bot, company, groupBy, granularity);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#getAgentTraffic");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **bot** | **String**| Filter by bot slug (e.g. gptbot, claudebot, perplexitybot) | [optional] |
| **company** | **String**| Filter by company (e.g. openai, anthropic, google) | [optional] |
| **groupBy** | **String**|  | [optional] [default to bot] [enum: bot, company] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |

### Return type

ApiResponse<[**AgentTrafficResponse**](AgentTrafficResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Agent traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |


## getAiTraffic

> void getAiTraffic(projectId, range, from, to, source, granularity)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible, Matomo or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String source = "source_example"; // String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
        String granularity = "day"; // String | 
        try {
            apiInstance.getAiTraffic(projectId, range, from, to, source, granularity);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#getAiTraffic");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source** | **String**| Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |

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
| **200** | AI referral traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |

## getAiTrafficWithHttpInfo

> ApiResponse<Void> getAiTrafficWithHttpInfo(projectId, range, from, to, source, granularity)

AI referral traffic (Scale plan or above)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible, Matomo or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String source = "source_example"; // String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
        String granularity = "day"; // String | 
        try {
            ApiResponse<Void> response = apiInstance.getAiTrafficWithHttpInfo(projectId, range, from, to, source, granularity);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#getAiTraffic");
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
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
| **source** | **String**| Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude) | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |

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
| **200** | AI referral traffic data |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |


## listAgentBots

> AgentBotsResponse listAgentBots(projectId, output)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            AgentBotsResponse result = apiInstance.listAgentBots(projectId, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#listAgentBots");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**AgentBotsResponse**](AgentBotsResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bot catalog |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

## listAgentBotsWithHttpInfo

> ApiResponse<AgentBotsResponse> listAgentBotsWithHttpInfo(projectId, output)

AI bot catalog (Scale plan or above)

Static catalog of AI bots that Agent Analytics can identify. Useful for rendering filter UIs that mirror our internal classification (slug, display name, company, category, Cloudflare verified-bot mapping, description). Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED. The equivalent MCP tool list_agent_bots is available on the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.AiAgentTrafficApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        AiAgentTrafficApi apiInstance = new AiAgentTrafficApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<AgentBotsResponse> response = apiInstance.listAgentBotsWithHttpInfo(projectId, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling AiAgentTrafficApi#listAgentBots");
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
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**AgentBotsResponse**](AgentBotsResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Bot catalog |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

