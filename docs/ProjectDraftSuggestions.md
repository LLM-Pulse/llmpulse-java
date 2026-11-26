

# ProjectDraftSuggestions

AI suggestions for a step. Only the key of the suggested step is sent, and only when status is ready

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**step** | **String** | The step the suggestions are for (details, prompts or competitors) |  [optional] |
|**status** | **String** | ready, none (not requested, or nothing cached yet) or failed |  |
|**details** | [**ProjectDraftSuggestionsDetails**](ProjectDraftSuggestionsDetails.md) |  |  [optional] |
|**prompts** | **List&lt;String&gt;** |  |  [optional] |
|**competitors** | [**List&lt;ProjectDraftSuggestionsCompetitorsInner&gt;**](ProjectDraftSuggestionsCompetitorsInner.md) |  |  [optional] |



