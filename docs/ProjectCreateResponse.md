

# ProjectCreateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**draftId** | **String** | The finalized draft; only present on POST /project_drafts/{id}/finalize |  [optional] |
|**project** | **Object** | Same shape as GET /dimensions/projects/{id} |  [optional] |
|**prompts** | [**ProjectCreateResponsePrompts**](ProjectCreateResponsePrompts.md) |  |  [optional] |
|**competitors** | [**ProjectCreateResponseCompetitors**](ProjectCreateResponseCompetitors.md) |  |  [optional] |
|**collections** | [**List&lt;ProjectCreateResponseCollectionsInner&gt;**](ProjectCreateResponseCollectionsInner.md) | Collections created from the request&#39;s collections field (empty when none were sent; absent on an idempotent replay) |  [optional] |
|**sameDomainProjects** | [**List&lt;ProjectCreateResponseSameDomainProjectsInner&gt;**](ProjectCreateResponseSameDomainProjectsInner.md) | Projects the caller can already see on the same domain (absent on an idempotent replay). Informational only: the create is never blocked, since one domain tracked per market is a normal setup. |  [optional] |
|**emailSubscription** | [**ProjectCreateResponseEmailSubscription**](ProjectCreateResponseEmailSubscription.md) |  |  [optional] |
|**limits** | [**ProjectCreateResponseLimits**](ProjectCreateResponseLimits.md) |  |  [optional] |
|**idempotent** | **Boolean** | Present and true only on external_identifier replays |  [optional] |
|**requestId** | **String** |  |  [optional] |



