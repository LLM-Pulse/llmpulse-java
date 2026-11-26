

# AnalystScoreRow

One analyst model's score of one brand (a subject in a custom study) on one attribute of one dimension

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**brand** | **String** | Brand name; the subject name in a custom study |  |
|**isProject** | **Boolean** | Whether it is the project&#39;s own brand; in a custom study, the focus subject |  |
|**model** | [**ModelEnum**](#ModelEnum) |  |  |
|**reportDate** | **LocalDate** |  |  |
|**dimension** | **String** | Dimension key, as the dimension filter takes it |  |
|**dimensionName** | **String** |  |  |
|**attribute** | **String** | Attribute key within the dimension |  |
|**attributeName** | **String** |  |  |
|**score** | **Object** | The 0-100 score as the analyst model wrote it, normally a number, or null when it gave none. Deliberately untyped, as the model&#39;s output is stored without coercion |  |
|**reasoning** | **String** | Why the model gave this score; null when it gave no reasoning |  |



## Enum: ModelEnum

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| GEMINI | &quot;gemini&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| GROK | &quot;grok&quot; |
| CLAUDE | &quot;claude&quot; |



