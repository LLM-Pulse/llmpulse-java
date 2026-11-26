

# SourceRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**promptExecutionId** | **Integer** |  |  |
|**domain** | **String** | Registrable domain of the cited URL |  |
|**url** | **String** | Normalized cited URL (tracking parameters and fragment removed) |  |
|**urlSha256** | **String** | Key of the cited page, as GET /citation_intelligence/urls/{url_sha256} takes it |  |
|**position** | **Integer** | Rank of the citation in the answer; 0 for a background source reference with no visible rank |  |
|**sourceType** | **String** | owned (the project&#39;s domains), competitor or third_party |  |
|**isGooglePlayLink** | **Boolean** |  |  |
|**isAppStoreLink** | **Boolean** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |



