

# ProjectCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**websiteUrl** | **URI** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
|**name** | **String** | Project name, as plain text. It can be changed later with PATCH /projects/{id} |  |
|**mainCountry** | **String** |  |  |
|**mainLanguage** | **String** |  |  |
|**brandName** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**industry** | **List&lt;String&gt;** | Industry keys, case-insensitive; a single key string is also accepted. An unknown key returns ERR_INVALID_PARAM listing the valid keys (the same list as the in-app industry picker, e.g. TECHNOLOGY, SAAS, ECOMMERCE) |  [optional] |
|**businessModel** | **String** | Business model key (e.g. B2B_SAAS, MARKETPLACE); unknown keys are rejected |  [optional] |
|**businessModelOther** | **String** | Free-text business model, only accepted when business_model is OTHER; rejected against any other key |  [optional] |
|**targetAudience** | **String** | Who the brand sells to. Context for Recommendations and GEO Writer (Brand Book) |  [optional] |
|**brandVoice** | **String** | Tone of voice guidance for generated content (Brand Book) |  [optional] |
|**goals** | **String** | What the brand wants to achieve. Context for GEO Writer and prompt suggestions |  [optional] |
|**primaryProducts** | **List&lt;String&gt;** | Main products or services |  [optional] |
|**matchingNames** | **List&lt;String&gt;** | Brand-name variants used to detect mentions. At most 50 names of up to 100 characters each; a longer list or name is refused with ERR_INVALID_PARAM (422) and nothing is created |  [optional] |
|**prompts** | **List&lt;String&gt;** |  |  [optional] |
|**collections** | [**List&lt;ProjectCreateRequestCollectionsInner&gt;**](ProjectCreateRequestCollectionsInner.md) | Collections (prompt tags) created with the project, each tagging prompts of this request by their exact text, so no separate tagging calls are needed. A text that is not in prompts returns ERR_INVALID_PARAM. A team member also needs Tags: Create permission. |  [optional] |
|**competitors** | [**List&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  |  [optional] |
|**ownedMedia** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  |  [optional] |
|**useSubdomain** | **Boolean** |  |  [optional] |
|**weeklyEmailSubscribed** | **Boolean** |  |  [optional] |
|**externalIdentifier** | **String** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account |  [optional] |
|**executePromptsImmediately** | **Boolean** |  |  [optional] |
|**pitch** | **Boolean** | Create a pitch project, a one-off snapshot for a prospect. It runs its prompts once across the account&#39;s AI models right away, takes no project slot and its prompts do not count against the prompt quota, and it is deleted 90 days later unless converted by sending pitch false to PATCH /projects/{id}. It uses one of the month&#39;s pitch projects (GET /account, limits.pitch_projects), needs an agency or platform account (GET /account, limits.pitch_projects.access) and a paid subscription on the Scale tier or higher, takes 1 to 100 prompts, and cannot use a domain the account already tracks or pitched in the last 90 days. execute_prompts_immediately must not be false |  [optional] |



