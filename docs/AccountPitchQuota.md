

# AccountPitchQuota

Pitch projects created this calendar month (Europe/Madrid) against the monthly allowance, which pitch projects use instead of a project slot. limit and remaining are null when unlimited is true.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**limit** | **Integer** |  |  [optional] |
|**used** | **Integer** |  |  [optional] |
|**remaining** | **Integer** |  |  [optional] |
|**unlimited** | **Boolean** |  |  [optional] |
|**period** | **String** | Always month |  [optional] |
|**resetsOn** | **LocalDate** | The first day of next month, when the allowance starts again |  [optional] |
|**access** | [**AccessEnum**](#AccessEnum) | Whether the account may create pitch projects, which are for agency and platform accounts (the account type, which the account owner or an account admin changes in Account Settings &gt; Profile). none means the account is not an agency; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0; revoked means our team turned it off. pending and rejected are no longer returned |  [optional] |



## Enum: AccessEnum

| Name | Value |
|---- | -----|
| NONE | &quot;none&quot; |
| PENDING | &quot;pending&quot; |
| APPROVED | &quot;approved&quot; |
| DORMANT | &quot;dormant&quot; |
| REJECTED | &quot;rejected&quot; |
| REVOKED | &quot;revoked&quot; |



