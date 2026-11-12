

# CustomReportDateRange


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**type** | [**TypeEnum**](#TypeEnum) | rolling (the last range_days days), previous_month (the previous calendar month), previous_3_months (the 3 calendar months before the current one) or custom (fixed dates, custom_from to custom_to) |  |
|**rangeDays** | **Integer** | Length of a rolling window; null for the other types |  |
|**customFrom** | **LocalDate** | First day chosen for a custom range; null for the other types |  |
|**customTo** | **LocalDate** | Last day chosen for a custom range, which can be after today; null for the other types |  |
|**from** | **LocalDate** | First day of the window as of now (detail only) |  [optional] |
|**to** | **LocalDate** | Last day of the window as of now (detail only); a custom range stops at today |  [optional] |
|**label** | **String** | The window as the report shows it (detail only) |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| ROLLING | &quot;rolling&quot; |
| PREVIOUS_MONTH | &quot;previous_month&quot; |
| PREVIOUS_3_MONTHS | &quot;previous_3_months&quot; |
| CUSTOM | &quot;custom&quot; |



