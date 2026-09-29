

# LlmsTxtTechnicalGeoReportResultData

The files and generation details once the report has completed; null before that

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**llmsTxtContent** | **String** | Current llms.txt, manual edits included |  [optional] |
|**llmsFullTxtContent** | **String** | Current llms-full.txt, manual edits included |  [optional] |
|**manuallyEditedAt** | **OffsetDateTime** | When the files were last edited by hand in the app, the API or MCP; null while they are as generated |  [optional] |
|**contentVersion** | **String** | Send it back as content_version when editing the files. It changes on every save |  [optional] |
|**originalLlmsTxtContent** | **String** | The generated llms.txt, kept from the first manual edit; null while the files are as generated |  [optional] |
|**originalLlmsFullTxtContent** | **String** | The generated llms-full.txt, kept from the first manual edit; null while the files are as generated |  [optional] |
|**crawlData** | **Object** |  |  [optional] |
|**metadata** | **Object** | Generation details, including output_language_code, the language the files were written in |  [optional] |
|**pagesCrawled** | **Integer** |  |  [optional] |
|**generationTimeMs** | **Integer** |  |  [optional] |
|**openaiTokensUsed** | **Integer** |  |  [optional] |



