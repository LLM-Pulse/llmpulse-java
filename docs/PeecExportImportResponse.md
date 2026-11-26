

# PeecExportImportResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**importId** | **Integer** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) | The import was accepted and finishes in the background |  |
|**prompts** | **Integer** | Distinct prompts of the file, per country and language; each becomes a tracked prompt of the project |  |
|**newPrompts** | **Integer** | The prompts the project does not hold yet, counted against the plan |  |
|**plannedAnswers** | **Integer** | Weekly answers the import files (prompts x tracked AI models x weeks) |  |
|**models** | **Map&lt;String, String&gt;** | Each AI model name of the file that is imported, with the tracked AI model its answers are filed under |  |
|**skippedModels** | **List&lt;String&gt;** | AI model names of the file whose answers are skipped, because the account does not track them |  |
|**detectedBrands** | **List&lt;String&gt;** | Brand names the export&#39;s mentions column lists (up to 50), none of them created as competitors |  |
|**appUrl** | **URI** | Opens the project&#39;s prompts in the app |  |
|**requestId** | **String** |  |  |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| STARTED | &quot;started&quot; |



