

# QueryFanOutRow

A view=query row carries query_text, count and share; a view=prompt row carries prompt_id, prompt_text, variations_count and total_count

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**queryText** | **String** | The sub-query a model issued (view&#x3D;query) |  [optional] |
|**count** | **Integer** | Times it was issued (view&#x3D;query) |  [optional] |
|**share** | **BigDecimal** | Share of all sub-query occurrences, on a 0-100 scale (view&#x3D;query) |  [optional] |
|**promptId** | **Integer** | view&#x3D;prompt |  [optional] |
|**promptText** | **String** | view&#x3D;prompt |  [optional] |
|**variationsCount** | **Integer** | Distinct sub-queries issued for the prompt (view&#x3D;prompt) |  [optional] |
|**totalCount** | **Integer** | Sub-queries issued for the prompt, repeats included (view&#x3D;prompt) |  [optional] |



