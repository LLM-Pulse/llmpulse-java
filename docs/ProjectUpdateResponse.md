

# ProjectUpdateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**project** | [**ProjectProfile**](ProjectProfile.md) |  |  |
|**updatedFields** | **List&lt;String&gt;** | The fields the request sent |  |
|**rematching** | **Boolean** | True when a matching_names or additional_owned_domains change started a background recalculation of past answers; further edits are rejected until it finishes |  |
|**note** | **String** | What the change does to mention detection, citation ownership and historical numbers, and, when prompt_limit was sent, how many prompts the project holds and how many more can be added |  |
|**requestId** | **String** |  |  |



