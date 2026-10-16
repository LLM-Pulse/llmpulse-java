

# ProjectProfile

The project name and profile, as PATCH /projects/{id} and the update_project MCP tool return them

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**name** | **String** |  |  |
|**brandName** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings. Deliberately untyped so generated clients decode either shape |  [optional] |
|**businessModel** | **String** |  |  [optional] |
|**businessModelOther** | **String** | Set only when business_model is OTHER |  [optional] |
|**targetAudience** | **String** |  |  [optional] |
|**primaryProducts** | **List&lt;String&gt;** |  |  [optional] |
|**brandVoice** | **String** |  |  [optional] |
|**goals** | **String** |  |  [optional] |
|**matchingNames** | **List&lt;String&gt;** |  |  |
|**additionalOwnedDomains** | **List&lt;String&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none |  |
|**promptLimit** | **Integer** | The most prompts this project can hold, set by the account owner or a co-owner (Account Settings &gt; Prompt Limits). Null when the project has no limit of its own; the account&#39;s plan allowance applies either way |  |



