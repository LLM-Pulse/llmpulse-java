

# ProjectCreateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**websiteUrl** | **URI** | Public HTTP(S) URL with a DNS hostname or public IP address. Credentials, private and special IP addresses, localhost and internal hostnames are rejected. |  |
|**name** | **String** |  |  |
|**mainCountry** | **String** |  |  |
|**mainLanguage** | **String** |  |  |
|**brandName** | **String** |  |  [optional] |
|**description** | **String** |  |  [optional] |
|**industry** | **List&lt;String&gt;** |  |  [optional] |
|**matchingNames** | **List&lt;String&gt;** |  |  [optional] |
|**prompts** | **List&lt;String&gt;** |  |  [optional] |
|**competitors** | [**List&lt;ProjectCreateRequestCompetitorsInner&gt;**](ProjectCreateRequestCompetitorsInner.md) |  |  [optional] |
|**ownedMedia** | [**ProjectCreateRequestOwnedMedia**](ProjectCreateRequestOwnedMedia.md) |  |  [optional] |
|**useSubdomain** | **Boolean** |  |  [optional] |
|**weeklyEmailSubscribed** | **Boolean** |  |  [optional] |
|**externalIdentifier** | **String** | Embed-enabled (Enterprise) accounts only; other accounts receive ERR_PLAN_REQUIRED. Idempotency key and embed-session join key, unique per account |  [optional] |
|**executePromptsImmediately** | **Boolean** |  |  [optional] |



