# MetricsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAgentTraffic**](MetricsApi.md#getAgentTraffic) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta) |
| [**getAgentTrafficWithHttpInfo**](MetricsApi.md#getAgentTrafficWithHttpInfo) | **GET** /metrics/agent_traffic | AI bot crawler traffic (Scale+, Beta) |
| [**getAiTraffic**](MetricsApi.md#getAiTraffic) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+) |
| [**getAiTrafficWithHttpInfo**](MetricsApi.md#getAiTrafficWithHttpInfo) | **GET** /metrics/ai_traffic | AI referral traffic (Scale+) |
| [**getPromptSummary**](MetricsApi.md#getPromptSummary) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**getPromptSummaryWithHttpInfo**](MetricsApi.md#getPromptSummaryWithHttpInfo) | **GET** /metrics/prompt_summary | Per-prompt metrics summary |
| [**getShareOfVoice**](MetricsApi.md#getShareOfVoice) | **GET** /metrics/sov | Share of Voice |
| [**getShareOfVoiceWithHttpInfo**](MetricsApi.md#getShareOfVoiceWithHttpInfo) | **GET** /metrics/sov | Share of Voice |
| [**getSummary**](MetricsApi.md#getSummary) | **GET** /metrics/summary | Aggregated metrics summary |
| [**getSummaryWithHttpInfo**](MetricsApi.md#getSummaryWithHttpInfo) | **GET** /metrics/summary | Aggregated metrics summary |
| [**getTimeseries**](MetricsApi.md#getTimeseries) | **GET** /metrics/timeseries | Time-series metrics |
| [**getTimeseriesWithHttpInfo**](MetricsApi.md#getTimeseriesWithHttpInfo) | **GET** /metrics/timeseries | Time-series metrics |
| [**getTopSources**](MetricsApi.md#getTopSources) | **GET** /metrics/top_sources | Top cited sources |
| [**getTopSourcesWithHttpInfo**](MetricsApi.md#getTopSourcesWithHttpInfo) | **GET** /metrics/top_sources | Top cited sources |



## getAgentTraffic

> AgentTrafficResponse getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity)

AI bot crawler traffic (Scale+, Beta)

Aggregated AI bot traffic hitting the project&#39;s origin server (GPTBot, PerplexityBot, ClaudeBot, OAI-SearchBot, Google-Extended, etc.). Sourced from Cloudflare or CSV uploads. Requires the Scale plan; lower tiers receive ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String bot = "bot_example"; // String | Filter by bot slug (e.g. gptbot, claudebot, perplexitybot)
        String company = "company_example"; // String | Filter by company (e.g. openai, anthropic, google)
        String groupBy = "bot"; // String | 
        String granularity = "day"; // String | 
        try {
            AgentTrafficResponse result = apiInstance.getAgentTraffic(projectId, range, from, to, bot, company, groupBy, granularity);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getAgentTraffic");
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
| **to** | **OffsetDateTime**|  | [optional] |
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

AI bot crawler traffic (Scale+, Beta)

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
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
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
            System.err.println("Exception when calling MetricsApi#getAgentTraffic");
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
| **to** | **OffsetDateTime**|  | [optional] |
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

AI referral traffic (Scale+)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String source = "source_example"; // String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
        String granularity = "day"; // String | 
        try {
            apiInstance.getAiTraffic(projectId, range, from, to, source, granularity);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getAiTraffic");
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
| **to** | **OffsetDateTime**|  | [optional] |
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

AI referral traffic (Scale+)

AI referral traffic for a project: human visits arriving from AI assistants (ChatGPT, Perplexity, Gemini, Claude, etc.), measured from the connected web analytics provider (Google Analytics 4, Adobe Analytics, PostHog, Plausible or Piano). Returns per-source users, sessions and conversions with totals and a conversion rate. Requires a connected provider and the Scale plan; otherwise returns ERR_AI_TRAFFIC_NOT_CONNECTED or ERR_PLAN_REQUIRED.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String source = "source_example"; // String | Filter by a single AI source slug (e.g. chatgpt, perplexity, gemini, claude)
        String granularity = "day"; // String | 
        try {
            ApiResponse<Void> response = apiInstance.getAiTrafficWithHttpInfo(projectId, range, from, to, source, granularity);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getAiTraffic");
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
| **to** | **OffsetDateTime**|  | [optional] |
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


## getPromptSummary

> PromptSummaryResponse getPromptSummary(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output)

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass &#x60;breakdown&#x3D;model&#x60; to split each prompt by model.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String breakdown = "model"; // String | Add per-(prompt, model) rows to the output
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String sort = "responses"; // String | 
        String sortDir = "asc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            PromptSummaryResponse result = apiInstance.getPromptSummary(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getPromptSummary");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **breakdown** | **String**| Add per-(prompt, model) rows to the output | [optional] [enum: model] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **String**|  | [optional] [default to responses] [enum: responses, mentions, citations, mention_rate, visibility, citation_rate, avg_mention_position, avg_position] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**PromptSummaryResponse**](PromptSummaryResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-prompt metrics |  -  |
| **401** | Authentication failed |  -  |

## getPromptSummaryWithHttpInfo

> ApiResponse<PromptSummaryResponse> getPromptSummaryWithHttpInfo(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output)

Per-prompt metrics summary

Paginated per-prompt aggregated metrics. Returns responses, mentions, citations, mention_rate, citation_rate, avg_mention_position and avg_position per prompt. Citations and citation rate include visible citations and background source references; avg_position uses visible citations only. Pass &#x60;breakdown&#x3D;model&#x60; to split each prompt by model.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String breakdown = "model"; // String | Add per-(prompt, model) rows to the output
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String sort = "responses"; // String | 
        String sortDir = "asc"; // String | 
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<PromptSummaryResponse> response = apiInstance.getPromptSummaryWithHttpInfo(projectId, range, from, to, breakdown, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, sortDir, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getPromptSummary");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **breakdown** | **String**| Add per-(prompt, model) rows to the output | [optional] [enum: model] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **String**|  | [optional] [default to responses] [enum: responses, mentions, citations, mention_rate, visibility, citation_rate, avg_mention_position, avg_position] |
| **sortDir** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**PromptSummaryResponse**](PromptSummaryResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Per-prompt metrics |  -  |
| **401** | Authentication failed |  -  |


## getShareOfVoice

> SovResponse getShareOfVoice(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view)

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        String view = "over_time"; // String | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others.
        try {
            SovResponse result = apiInstance.getShareOfVoice(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getShareOfVoice");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **view** | **String**| Which Share of Voice projection to flatten. Only valid together with &#39;output&#39;. &#39;over_time&#39; (default) is one row per date and actor, &#39;current&#39; the ranked snapshot, &#39;breakdown&#39; the Top 4 plus Others. | [optional] [default to over_time] [enum: over_time, current, breakdown] |

### Return type

[**SovResponse**](SovResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Share of voice data |  -  |

## getShareOfVoiceWithHttpInfo

> ApiResponse<SovResponse> getShareOfVoiceWithHttpInfo(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view)

Share of Voice

Share of Voice breakdown comparing your project to competitors. Returns over_time, current snapshot, and a Top-4 + Others breakdown.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String granularity = "day"; // String | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        String view = "over_time"; // String | Which Share of Voice projection to flatten. Only valid together with 'output'. 'over_time' (default) is one row per date and actor, 'current' the ranked snapshot, 'breakdown' the Top 4 plus Others.
        try {
            ApiResponse<SovResponse> response = apiInstance.getShareOfVoiceWithHttpInfo(projectId, range, from, to, granularity, competitors, model, collectionId, prompt, promptType, brandKind, output, view);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getShareOfVoice");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |
| **view** | **String**| Which Share of Voice projection to flatten. Only valid together with &#39;output&#39;. &#39;over_time&#39; (default) is one row per date and actor, &#39;current&#39; the ranked snapshot, &#39;breakdown&#39; the Top 4 plus Others. | [optional] [default to over_time] [enum: over_time, current, breakdown] |

### Return type

ApiResponse<[**SovResponse**](SovResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Share of voice data |  -  |


## getSummary

> SummaryResponse getSummary(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output)

Aggregated metrics summary

Same as /metrics/timeseries but adds a &#x60;summary&#x60; block with total/min/max/last per metric per actor, plus a &#x60;position_distribution&#x60; block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. &#x60;total&#x60; is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an &#x60;aggregation&#x60; field (&#x60;sum&#x60; or &#x60;average&#x60;).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String metrics = "metrics_example"; // String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
        String granularity = "day"; // String | 
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            SummaryResponse result = apiInstance.getSummary(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getSummary");
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
| **metrics** | **String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**SummaryResponse**](SummaryResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary metrics |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |

## getSummaryWithHttpInfo

> ApiResponse<SummaryResponse> getSummaryWithHttpInfo(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output)

Aggregated metrics summary

Same as /metrics/timeseries but adds a &#x60;summary&#x60; block with total/min/max/last per metric per actor, plus a &#x60;position_distribution&#x60; block (Position 1, Position 2, Position 3+). Citations and citation rate include visible citations and background source references. Background references use position 0 and are excluded from avg_position and position distributions. &#x60;total&#x60; is a SUM for count metrics (mentions, citations, responses) and an AVERAGE across periods for rate/percentage and average metrics (visibility/mention_rate, citation_rate, ai_visibility_score, sentiment shares, avg_position, avg_mention_position, net_sentiment); rates are never summed. Each summary row carries an &#x60;aggregation&#x60; field (&#x60;sum&#x60; or &#x60;average&#x60;).

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String metrics = "metrics_example"; // String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
        String granularity = "day"; // String | 
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<SummaryResponse> response = apiInstance.getSummaryWithHttpInfo(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, prompt, promptType, brandKind, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getSummary");
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
| **metrics** | **String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**SummaryResponse**](SummaryResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Summary metrics |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |


## getTimeseries

> TimeseriesResponse getTimeseries(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output)

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String metrics = "metrics_example"; // String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
        String granularity = "day"; // String | 
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Boolean includeProject = true; // Boolean | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            TimeseriesResponse result = apiInstance.getTimeseries(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getTimeseries");
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
| **metrics** | **String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **includeProject** | **Boolean**|  | [optional] [default to true] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**TimeseriesResponse**](TimeseriesResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Time-series data |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

## getTimeseriesWithHttpInfo

> ApiResponse<TimeseriesResponse> getTimeseriesWithHttpInfo(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output)

Time-series metrics

Returns time-series data for one or more metrics, broken down by actor (project + competitors). Supports day/week/month granularity, with sticky carry-forward semantics for week/month aggregates.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String metrics = "metrics_example"; // String | Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only.
        String granularity = "day"; // String | 
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String competitors = "competitors_example"; // String | Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM)
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Boolean includeProject = true; // Boolean | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<TimeseriesResponse> response = apiInstance.getTimeseriesWithHttpInfo(projectId, metrics, granularity, range, from, to, competitors, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, includeProject, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getTimeseries");
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
| **metrics** | **String**| Comma-separated list of metrics: mentions, citations, responses, mention_rate, visibility (alias for mention_rate), weighted_visibility, ai_visibility_score (alias for weighted_visibility), citation_rate, avg_position, avg_mention_position, net_sentiment, sentiment_very_positive, sentiment_positive, sentiment_neutral, sentiment_negative, sentiment_very_negative. Citations and citation_rate include visible citations and background source references; avg_position uses visible citations only. | [optional] |
| **granularity** | **String**|  | [optional] [enum: day, week, month] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**|  | [optional] |
| **competitors** | **String**| Comma-separated competitor IDs (unknown IDs return ERR_INVALID_PARAM) | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **includeProject** | **Boolean**|  | [optional] [default to true] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**TimeseriesResponse**](TimeseriesResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Time-series data |  -  |
| **401** | Authentication failed |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |


## getTopSources

> TopSourcesResponse getTopSources(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output)

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String sort = "total_responses"; // String | 
        String query = "query_example"; // String | Filter domains by case-insensitive partial match
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            TopSourcesResponse result = apiInstance.getTopSources(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getTopSources");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **String**|  | [optional] [default to total_responses] [enum: total_responses, avg_mention_rate, avg_visibility] |
| **query** | **String**| Filter domains by case-insensitive partial match | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

[**TopSourcesResponse**](TopSourcesResponse.md)


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top sources |  -  |

## getTopSourcesWithHttpInfo

> ApiResponse<TopSourcesResponse> getTopSourcesWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output)

Top cited sources

Registrable domains most frequently cited in AI responses for the project, including visible citations and background source references. This endpoint remains a domain rollup when exact-subdomain matching is enabled. Results can be sorted by total responses, average mention rate, or average visibility.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.MetricsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        MetricsApi apiInstance = new MetricsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        Integer collectionId = 56; // Integer | 
        String countryCode = "countryCode_example"; // String | ISO country code (e.g. US, GB, DE)
        String languageCode = "languageCode_example"; // String | ISO language code (e.g. en, es, de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "informational"; // String | Filter by prompt type (search intent)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        String sort = "total_responses"; // String | 
        String query = "query_example"; // String | Filter domains by case-insensitive partial match
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<TopSourcesResponse> response = apiInstance.getTopSourcesWithHttpInfo(projectId, range, from, to, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, sort, query, page, perPage, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
            System.out.println("Response body: " + response.getData());
        } catch (ApiException e) {
            System.err.println("Exception when calling MetricsApi#getTopSources");
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
| **to** | **OffsetDateTime**|  | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus] |
| **collectionId** | **Integer**|  | [optional] |
| **countryCode** | **String**| ISO country code (e.g. US, GB, DE) | [optional] |
| **languageCode** | **String**| ISO language code (e.g. en, es, de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| Filter by prompt type (search intent) | [optional] [enum: informational, navigational, commercial, transactional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **sort** | **String**|  | [optional] [default to total_responses] [enum: total_responses, avg_mention_rate, avg_visibility] |
| **query** | **String**| Filter domains by case-insensitive partial match | [optional] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **output** | **String**| Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional] [enum: flat, csv] |

### Return type

ApiResponse<[**TopSourcesResponse**](TopSourcesResponse.md)>


### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Top sources |  -  |

