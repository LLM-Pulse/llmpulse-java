# ShoppingAdsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listAds**](ShoppingAdsApi.md#listAds) | **GET** /dimensions/ads | List AI ad placements |
| [**listAdsWithHttpInfo**](ShoppingAdsApi.md#listAdsWithHttpInfo) | **GET** /dimensions/ads | List AI ad placements |
| [**listShopping**](ShoppingAdsApi.md#listShopping) | **GET** /dimensions/shopping | List shopping results |
| [**listShoppingWithHttpInfo**](ShoppingAdsApi.md#listShoppingWithHttpInfo) | **GET** /dimensions/shopping | List shopping results |



## listAds

> void listAds(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List AI ad placements

Paid placements returned inside AI answers. view&#x3D;advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view&#x3D;ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ShoppingAdsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ShoppingAdsApi apiInstance = new ShoppingAdsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "advertisers"; // String | Row shape: one per advertising domain, or one per placement
        Boolean owned = true; // Boolean | Return only placements identified as the tracked brand's own (view=ads)
        String order = "ads"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | Sort direction for view=advertisers. Defaults to desc, except avg_position and domain which default to asc.
        String query = "query_example"; // String | Case-insensitive substring filter on the ad title, domain or snippet
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        GetTimeseriesCollectionIdParameter collectionId = new GetTimeseriesCollectionIdParameter(); // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listAds(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ShoppingAdsApi#listAds");
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
| **view** | **String**| Row shape: one per advertising domain, or one per placement | [optional] [default to advertisers] [enum: advertisers, ads] |
| **owned** | **Boolean**| Return only placements identified as the tracked brand&#39;s own (view&#x3D;ads) | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: ads, prompts, avg_position, domain, recent, oldest, position] |
| **direction** | **String**| Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [optional] [enum: asc, desc] |
| **query** | **String**| Case-insensitive substring filter on the ad title, domain or snippet | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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
| **200** | Paginated ad rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

## listAdsWithHttpInfo

> ApiResponse<Void> listAdsWithHttpInfo(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List AI ad placements

Paid placements returned inside AI answers. view&#x3D;advertisers (default) returns one row per advertising domain with its placement count, prompt reach and average and best position; view&#x3D;ads returns the individual placements with title, snippet, position and the prompt that triggered them. Position 1 is the best slot, so a LOWER average position is better. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ShoppingAdsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ShoppingAdsApi apiInstance = new ShoppingAdsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "advertisers"; // String | Row shape: one per advertising domain, or one per placement
        Boolean owned = true; // Boolean | Return only placements identified as the tracked brand's own (view=ads)
        String order = "ads"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | Sort direction for view=advertisers. Defaults to desc, except avg_position and domain which default to asc.
        String query = "query_example"; // String | Case-insensitive substring filter on the ad title, domain or snippet
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        GetTimeseriesCollectionIdParameter collectionId = new GetTimeseriesCollectionIdParameter(); // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listAdsWithHttpInfo(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ShoppingAdsApi#listAds");
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
| **view** | **String**| Row shape: one per advertising domain, or one per placement | [optional] [default to advertisers] [enum: advertisers, ads] |
| **owned** | **Boolean**| Return only placements identified as the tracked brand&#39;s own (view&#x3D;ads) | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: ads, prompts, avg_position, domain, recent, oldest, position] |
| **direction** | **String**| Sort direction for view&#x3D;advertisers. Defaults to desc, except avg_position and domain which default to asc. | [optional] [enum: asc, desc] |
| **query** | **String**| Case-insensitive substring filter on the ad title, domain or snippet | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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
| **200** | Paginated ad rows plus totals |  -  |
| **422** | Invalid parameters |  -  |


## listShopping

> void listShopping(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List shopping results

Product cards returned inside AI answers. view&#x3D;products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view&#x3D;merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ShoppingAdsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ShoppingAdsApi apiInstance = new ShoppingAdsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "products"; // String | Row shape: one per distinct product, or one per merchant
        Boolean owned = true; // Boolean | Return only products identified as the tracked brand's own. On view=merchants this narrows to the merchants selling those products; the totals block stays account-wide.
        String order = "appearances"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | 
        String query = "query_example"; // String | Case-insensitive substring filter on the product title
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        GetTimeseriesCollectionIdParameter collectionId = new GetTimeseriesCollectionIdParameter(); // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            apiInstance.listShopping(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output);
        } catch (ApiException e) {
            System.err.println("Exception when calling ShoppingAdsApi#listShopping");
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
| **view** | **String**| Row shape: one per distinct product, or one per merchant | [optional] [default to products] [enum: products, merchants] |
| **owned** | **Boolean**| Return only products identified as the tracked brand&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: appearances, price, rating, title, products, avg_price, avg_rating, merchant] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **query** | **String**| Case-insensitive substring filter on the product title | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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
| **200** | Paginated shopping rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

## listShoppingWithHttpInfo

> ApiResponse<Void> listShoppingWithHttpInfo(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output)

List shopping results

Product cards returned inside AI answers. view&#x3D;products (default) returns one row per distinct product, merged across executions, with its appearance count, price range, rating and whether it is yours, plus a currency_count saying how many currencies it was priced in (above 1 means the row reports its highest-priced listing and min_price may be another currency); view&#x3D;merchants returns one row per selling merchant, with a currency field naming the money its price range and average are expressed in (providers price each market in its own currency, so a merchant that sells in more than one reports the currency most of its prices use). Every response also carries a totals block matching the KPI cards in the app, whose avg_price is computed inside the single currency named by avg_price_currency. Requires the Scale plan or above.

### Example

```java
// Import classes:
import ai.llmpulse.sdk.ApiClient;
import ai.llmpulse.sdk.ApiException;
import ai.llmpulse.sdk.ApiResponse;
import ai.llmpulse.sdk.Configuration;
import ai.llmpulse.sdk.auth.*;
import ai.llmpulse.sdk.models.*;
import ai.llmpulse.sdk.api.ShoppingAdsApi;

public class Example {
    public static void main(String[] args) {
        ApiClient defaultClient = Configuration.getDefaultApiClient();
        defaultClient.setBasePath("https://api.llmpulse.ai/api/v1");
        
        // Configure HTTP bearer authorization: BearerAuth
        HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
        BearerAuth.setBearerToken("BEARER TOKEN");

        ShoppingAdsApi apiInstance = new ShoppingAdsApi(defaultClient);
        Integer projectId = 56; // Integer | Project ID
        Integer page = 1; // Integer | 
        Integer perPage = 20; // Integer | 
        String view = "products"; // String | Row shape: one per distinct product, or one per merchant
        Boolean owned = true; // Boolean | Return only products identified as the tracked brand's own. On view=merchants this narrows to the merchants selling those products; the totals block stays account-wide.
        String order = "appearances"; // String | Sort field; the allowed set depends on view
        String direction = "asc"; // String | 
        String query = "query_example"; // String | Case-insensitive substring filter on the product title
        String model = "chatgpt"; // String | Filter by AI model. Models the API key's user has not enabled are silently dropped.
        GetTimeseriesCollectionIdParameter collectionId = new GetTimeseriesCollectionIdParameter(); // GetTimeseriesCollectionIdParameter | One collection/tag ID or a comma-separated list of IDs
        String countryCode = "countryCode_example"; // String | One ISO country code or a comma-separated list (e.g. US,GB,DE)
        String languageCode = "languageCode_example"; // String | One ISO language code or a comma-separated list (e.g. en,es,de)
        Integer prompt = 56; // Integer | Filter by prompt ID
        String promptType = "promptType_example"; // String | One prompt type or a comma-separated list: informational, navigational, commercial, transactional
        String brandKind = "brand"; // String | Filter by brand kind: brand (own brand/products), brand_other (competitors/other brands), non_brand (generic, no brand named). For fair 1:1 brand-vs-competitor comparisons (visibility, share of voice), use non_brand: brand-focused prompts skew results toward the brand they name. The in-app Overview page applies non_brand by default.
        Integer range = 56; // Integer | Number of days to look back (alternative to from/to)
        OffsetDateTime from = OffsetDateTime.now(); // OffsetDateTime | 
        OffsetDateTime to = OffsetDateTime.now(); // OffsetDateTime | End of the window. A date-only value such as 2026-09-01 covers that whole day. Pass a full timestamp to end the window earlier.
        String output = "flat"; // String | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. 'flat' returns the same metadata plus 'columns' and 'rows'; 'csv' returns those rows as text/csv. Errors are always returned as JSON.
        try {
            ApiResponse<Void> response = apiInstance.listShoppingWithHttpInfo(projectId, page, perPage, view, owned, order, direction, query, model, collectionId, countryCode, languageCode, prompt, promptType, brandKind, range, from, to, output);
            System.out.println("Status code: " + response.getStatusCode());
            System.out.println("Response headers: " + response.getHeaders());
        } catch (ApiException e) {
            System.err.println("Exception when calling ShoppingAdsApi#listShopping");
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
| **view** | **String**| Row shape: one per distinct product, or one per merchant | [optional] [default to products] [enum: products, merchants] |
| **owned** | **Boolean**| Return only products identified as the tracked brand&#39;s own. On view&#x3D;merchants this narrows to the merchants selling those products; the totals block stays account-wide. | [optional] |
| **order** | **String**| Sort field; the allowed set depends on view | [optional] [enum: appearances, price, rating, title, products, avg_price, avg_rating, merchant] |
| **direction** | **String**|  | [optional] [default to desc] [enum: asc, desc] |
| **query** | **String**| Case-insensitive substring filter on the product title | [optional] |
| **model** | **String**| Filter by AI model. Models the API key&#39;s user has not enabled are silently dropped. | [optional] [enum: chatgpt, perplexity, gemini, ai_overview, ai_mode, copilot, claude, grok, deepseek, meta_ai, amazon_rufus, naver_ai, baidu_ai] |
| **collectionId** | [**GetTimeseriesCollectionIdParameter**](.md)| One collection/tag ID or a comma-separated list of IDs | [optional] |
| **countryCode** | **String**| One ISO country code or a comma-separated list (e.g. US,GB,DE) | [optional] |
| **languageCode** | **String**| One ISO language code or a comma-separated list (e.g. en,es,de) | [optional] |
| **prompt** | **Integer**| Filter by prompt ID | [optional] |
| **promptType** | **String**| One prompt type or a comma-separated list: informational, navigational, commercial, transactional | [optional] |
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
| **200** | Paginated shopping rows plus totals |  -  |
| **422** | Invalid parameters |  -  |

