

# PromptGenerationRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**source** | [**SourceEnum**](#SourceEnum) | Which Add prompts generator to run |  |
|**query** | **String** | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type&#x3D;brand). paa: one keyword, as an alternative to keywords. |  [optional] |
|**count** | **Integer** | keyword and topic: how many suggestions to ask for, capped by the prompt slots left |  [optional] |
|**countryCode** | **String** | ISO 3166-1 alpha-2 country of the suggestions (default the project country) |  [optional] |
|**languageCode** | **String** | ISO language code of the suggestions (default the project language) |  [optional] |
|**competitorId** | **Integer** | keyword: write the suggestions around this competitor of the project |  [optional] |
|**searchType** | [**SearchTypeEnum**](#SearchTypeEnum) | reddit: search discussions of a topic or a brand |  [optional] |
|**keywords** | **List&lt;String&gt;** | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account&#39;s 24-hour allowance |  [optional] |
|**sourceCountryCode** | **String** | translate: country of the prompts to translate |  [optional] |
|**sourceLanguageCode** | **String** | translate: language of the prompts to translate |  [optional] |
|**minWords** | **Integer** | search_console: skip queries shorter than this many words |  [optional] |
|**allCountries** | **Boolean** | search_console: include queries from every country instead of country_code only |  [optional] |



## Enum: SourceEnum

| Name | Value |
|---- | -----|
| WEBSITE | &quot;website&quot; |
| KEYWORD | &quot;keyword&quot; |
| TOPIC | &quot;topic&quot; |
| REDDIT | &quot;reddit&quot; |
| PAA | &quot;paa&quot; |
| REPUTATIONAL | &quot;reputational&quot; |
| TRANSLATE | &quot;translate&quot; |
| SEARCH_CONSOLE | &quot;search_console&quot; |



## Enum: SearchTypeEnum

| Name | Value |
|---- | -----|
| TOPIC | &quot;topic&quot; |
| BRAND | &quot;brand&quot; |



