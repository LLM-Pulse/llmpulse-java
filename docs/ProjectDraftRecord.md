

# ProjectDraftRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**draftId** | **String** | Draft id (draft_...) |  |
|**status** | **String** | open, finalized or expired |  |
|**currentStep** | **String** | The next step to submit (details, prompts, competitors, owned_media), or ready when the draft can be finalized |  |
|**stepsCompleted** | **List&lt;String&gt;** |  |  |
|**stepsRemaining** | **List&lt;String&gt;** | Required steps not submitted yet |  |
|**optionalSteps** | **List&lt;String&gt;** | Steps the plan allows but finalize does not require (owned_media from Growth) |  |
|**finalizable** | **Boolean** |  |  |
|**websiteUrl** | **String** |  |  |
|**mainCountry** | **String** |  |  |
|**mainLanguage** | **String** |  |  |
|**useSubdomain** | **Boolean** |  |  |
|**name** | **String** | Null until the details step |  |
|**brandName** | **String** |  |  |
|**description** | **String** |  |  |
|**industry** | **List&lt;String&gt;** |  |  |
|**matchingNames** | **List&lt;String&gt;** |  |  |
|**prompts** | **List&lt;String&gt;** |  |  |
|**competitors** | [**List&lt;ProjectDraftRecordCompetitorsInner&gt;**](ProjectDraftRecordCompetitorsInner.md) |  |  |
|**ownedMedia** | [**ProjectDraftRecordOwnedMedia**](ProjectDraftRecordOwnedMedia.md) |  |  |
|**weeklyEmailSubscribed** | **Boolean** |  |  |
|**externalIdentifier** | **String** |  |  |
|**executePromptsImmediately** | **Boolean** |  |  |
|**projectId** | **Integer** | The project the draft became; null until finalized |  |
|**expiresAt** | **OffsetDateTime** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |



