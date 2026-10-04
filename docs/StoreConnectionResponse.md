

# StoreConnectionResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**platform** | **String** | The store platform, e.g. shopify |  |
|**domain** | **String** | The store domain as compared: lowercase, without scheme, www or path |  |
|**project** | [**StoreConnectionResponseProject**](StoreConnectionResponseProject.md) |  |  |
|**ambiguous** | **Boolean** | True when several live projects match the store domain (for example one project per market). project is then null and the app asks the key holder to pick from candidates. |  |
|**candidates** | [**List&lt;StoreConnectionResponseCandidatesInner&gt;**](StoreConnectionResponseCandidatesInner.md) | Every live project of the account, for a project picker |  |
|**account** | [**StoreConnectionResponseAccount**](StoreConnectionResponseAccount.md) |  |  |
|**requestId** | **String** |  |  |



