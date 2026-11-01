

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
|**access** | [**AccessEnum**](#AccessEnum) | Whether the account may create pitch projects. The account owner or an account admin (co-owner) requests access in Account Settings &gt; Pitch projects and our team reviews it; approved access goes dormant while the account is below the Scale tier, on a trial, has a payment problem, is set to cancel or has an allowance of 0 |  [optional] |



## Enum: AccessEnum

| Name | Value |
|---- | -----|
| NONE | &quot;none&quot; |
| PENDING | &quot;pending&quot; |
| APPROVED | &quot;approved&quot; |
| DORMANT | &quot;dormant&quot; |
| REJECTED | &quot;rejected&quot; |
| REVOKED | &quot;revoked&quot; |



