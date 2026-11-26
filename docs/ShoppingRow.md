

# ShoppingRow

One row of /dimensions/shopping. Fields depend on view: products (product_key, title, domain, url, merchants, currency, currency_count, min_price, max_price, avg_rating, rating_votes, appearances, is_client, best_rank, models, last_seen_at) and merchants (merchant, appearances, products, currency, min_price, max_price, avg_price, avg_rating).

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**productKey** | **String** | Stable grouping key of the product: its external id, else title: and the lowercased title (view&#x3D;products) |  [optional] |
|**title** | **String** |  |  [optional] |
|**domain** | **String** |  |  [optional] |
|**url** | **String** |  |  [optional] |
|**merchants** | **String** | The merchants the product card names (view&#x3D;products) |  [optional] |
|**merchant** | **String** | The merchant (view&#x3D;merchants) |  [optional] |
|**products** | **Integer** | Distinct products the merchant sold (view&#x3D;merchants) |  [optional] |
|**currency** | **String** | Currency code the prices are in; null when no price names one |  |
|**currencyCount** | **Integer** | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view&#x3D;products) |  [optional] |
|**minPrice** | **BigDecimal** |  |  |
|**maxPrice** | **BigDecimal** |  |  |
|**avgPrice** | **BigDecimal** | Average price in currency (view&#x3D;merchants) |  [optional] |
|**avgRating** | **BigDecimal** |  |  |
|**ratingVotes** | **Integer** | Most rating votes any listing of the product showed (view&#x3D;products) |  [optional] |
|**appearances** | **Integer** |  |  |
|**isClient** | **Boolean** | Whether the product is identified as your brand&#39;s own (view&#x3D;products) |  [optional] |
|**bestRank** | **Integer** | Best rank the product got in a card list (view&#x3D;products) |  [optional] |
|**models** | [**List&lt;ModelsEnum&gt;**](#List&lt;ModelsEnum&gt;) | Models that showed the product (view&#x3D;products) |  [optional] |
|**lastSeenAt** | **OffsetDateTime** | The latest answer that showed the product (view&#x3D;products) |  [optional] |



## Enum: List&lt;ModelsEnum&gt;

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| AI_MODE | &quot;ai_mode&quot; |
| AI_OVERVIEW | &quot;ai_overview&quot; |
| GEMINI | &quot;gemini&quot; |
| COPILOT | &quot;copilot&quot; |
| AMAZON_RUFUS | &quot;amazon_rufus&quot; |
| CLAUDE | &quot;claude&quot; |
| GROK | &quot;grok&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| NAVER_AI | &quot;naver_ai&quot; |
| BAIDU_AI | &quot;baidu_ai&quot; |
| META_AI | &quot;meta_ai&quot; |
| NAVER_AI_TAB | &quot;naver_ai_tab&quot; |
| QWEN | &quot;qwen&quot; |
| DOUBAO | &quot;doubao&quot; |
| BING_AI_MODE | &quot;bing_ai_mode&quot; |
| BING_AI_OVERVIEW | &quot;bing_ai_overview&quot; |



