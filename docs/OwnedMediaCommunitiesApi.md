# OwnedMediaCommunitiesApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listOwnedMedia**](OwnedMediaCommunitiesApi.md#listOwnedMedia) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listOwnedMediaWithHttpInfo**](OwnedMediaCommunitiesApi.md#listOwnedMediaWithHttpInfo) | **GET** /dimensions/owned_media | List owned-media citations |
| [**listRedditCitations**](OwnedMediaCommunitiesApi.md#listRedditCitations) | **GET** /dimensions/reddit | List cited Reddit content |
| [**listRedditCitationsWithHttpInfo**](OwnedMediaCommunitiesApi.md#listRedditCitationsWithHttpInfo) | **GET** /dimensions/reddit | List cited Reddit content |



## listOwnedMedia

> void listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. view&#x3D;own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.OwnedMediaCommunitiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        OwnedMediaCommunitiesApi apiInstance = new OwnedMediaCommunitiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String provider = "youtube"; // String | The platform to report on
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "videos"; // String | Row shape; the allowed set depends on provider
        String store = "google_play"; // String | provider=mobile_apps only
        Boolean owned = true; // Boolean | Return only rows belonging to the account's own connected profile
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listOwnedMedia(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling OwnedMediaCommunitiesApi#listOwnedMedia");
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
| **provider** | **String**| The platform to report on | [enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **view** | **String**| Row shape; the allowed set depends on provider | [optional] [enum: videos, channels, posts, profiles, own_citations, apps] |
| **store** | **String**| provider&#x3D;mobile_apps only | [optional] [default to google_play] [enum: google_play, app_store] |
| **owned** | **Boolean**| Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
| **200** | Paginated owned-media rows |  -  |
| **422** | Invalid parameters |  -  |

## listOwnedMediaWithHttpInfo

> ApiResponse<Void> listOwnedMediaWithHttpInfo(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List owned-media citations

Which owned-media content AI answers cite, by platform. &#x60;provider&#x60; is required. Each row carries a &#x60;yours&#x60; flag so you can compare your own presence against everyone else cited on the same platform. view&#x3D;own_citations returns the raw citations of the connected profile only and stays empty until a profile is connected. For Reddit use /dimensions/reddit. Requires the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.OwnedMediaCommunitiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        OwnedMediaCommunitiesApi apiInstance = new OwnedMediaCommunitiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        String provider = "youtube"; // String | The platform to report on
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "videos"; // String | Row shape; the allowed set depends on provider
        String store = "google_play"; // String | provider=mobile_apps only
        Boolean owned = true; // Boolean | Return only rows belonging to the account's own connected profile
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listOwnedMediaWithHttpInfo(projectId, provider, page, perPage, view, store, owned, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling OwnedMediaCommunitiesApi#listOwnedMedia");
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
| **provider** | **String**| The platform to report on | [enum: youtube, instagram, facebook, tiktok, linkedin, mobile_apps] |
| **page** | **Integer**|  | [optional] [default to 1] |
| **perPage** | **Integer**|  | [optional] [default to 20] |
| **view** | **String**| Row shape; the allowed set depends on provider | [optional] [enum: videos, channels, posts, profiles, own_citations, apps] |
| **store** | **String**| provider&#x3D;mobile_apps only | [optional] [default to google_play] [enum: google_play, app_store] |
| **owned** | **Boolean**| Return only rows belonging to the account&#39;s own connected profile | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
| **200** | Paginated owned-media rows |  -  |
| **422** | Invalid parameters |  -  |


## listRedditCitations

> void listRedditCitations(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view&#x3D;subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view&#x3D;authors returns one row per author; view&#x3D;threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.OwnedMediaCommunitiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        OwnedMediaCommunitiesApi apiInstance = new OwnedMediaCommunitiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "subreddits"; // String | 
        String subreddit = "subreddit_example"; // String | Filter to one subreddit (name without the r/ prefix)
        String author = "author_example"; // String | Filter to one Reddit author
        String status = "open"; // String | view=threads only
        Boolean owned = true; // Boolean | Return only subreddits/authors the account has claimed as its own
        String brand = "brand_example"; // String | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer.
        String order = "citations"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listRedditCitations(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling OwnedMediaCommunitiesApi#listRedditCitations");
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
| **view** | **String**|  | [optional] [default to subreddits] [enum: subreddits, authors, threads] |
| **subreddit** | **String**| Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **String**| Filter to one Reddit author | [optional] |
| **status** | **String**| view&#x3D;threads only | [optional] [enum: open, archived] |
| **owned** | **Boolean**| Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **String**| Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: citations, subreddit, unique_authors, positive_pct, negative_pct, author, avg_position, upvotes, comments, sentiment] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
| **200** | Paginated Reddit rows |  -  |
| **422** | Invalid parameters |  -  |

## listRedditCitationsWithHttpInfo

> ApiResponse<Void> listRedditCitationsWithHttpInfo(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output)

List cited Reddit content

Which Reddit content AI answers cite for your tracked prompts. view&#x3D;subreddits (default) returns one row per subreddit with its citation count, unique authors and positive/negative sentiment split; view&#x3D;authors returns one row per author; view&#x3D;threads returns the individual cited threads with upvotes, comments, average position and dominant sentiment. Requires the Growth plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.OwnedMediaCommunitiesApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        OwnedMediaCommunitiesApi apiInstance = new OwnedMediaCommunitiesApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "subreddits"; // String | 
        String subreddit = "subreddit_example"; // String | Filter to one subreddit (name without the r/ prefix)
        String author = "author_example"; // String | Filter to one Reddit author
        String status = "open"; // String | view=threads only
        Boolean owned = true; // Boolean | Return only subreddits/authors the account has claimed as its own
        String brand = "brand_example"; // String | Filter to citations whose scraped Reddit content mentions a brand: 'brand' for the tracked brand, or a competitor id. Reads the page content, not the AI answer.
        String order = "citations"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | 
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        String collectionId = "12,34"; // String | One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize.
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listRedditCitationsWithHttpInfo(projectId, page, perPage, view, subreddit, author, status, owned, brand, order, direction, model, collectionId, countryCode, languageCode, brandKind, range, from, to, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling OwnedMediaCommunitiesApi#listRedditCitations");
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
| **view** | **String**|  | [optional] [default to subreddits] [enum: subreddits, authors, threads] |
| **subreddit** | **String**| Filter to one subreddit (name without the r/ prefix) | [optional] |
| **author** | **String**| Filter to one Reddit author | [optional] |
| **status** | **String**| view&#x3D;threads only | [optional] [enum: open, archived] |
| **owned** | **Boolean**| Return only subreddits/authors the account has claimed as its own | [optional] |
| **brand** | **String**| Filter to citations whose scraped Reddit content mentions a brand: &#39;brand&#39; for the tracked brand, or a competitor id. Reads the page content, not the AI answer. | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: citations, subreddit, unique_authors, positive_pct, negative_pct, author, avg_position, upvotes, comments, sentiment] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, ai_mode, ai_overview, gemini, copilot, amazon_rufus, claude, grok, deepseek, naver_ai, baidu_ai, meta_ai] |
| **collectionId** | **String**| One collection/tag ID or a comma-separated list of IDs. A query value is always a string on the wire, so it is typed as one: the previous integer-or-string union made generators emit a wrapper type they could not serialize. | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **brandKind** | **String**| Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default. | [optional] [enum: brand, brand_other, non_brand] |
| **range** | **Integer**| Number of days to look back (alternative to from/to) | [optional] |
| **from** | **OffsetDateTime**|  | [optional] |
| **to** | **OffsetDateTime**| End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier. | [optional] |
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
| **200** | Paginated Reddit rows |  -  |
| **422** | Invalid parameters |  -  |

