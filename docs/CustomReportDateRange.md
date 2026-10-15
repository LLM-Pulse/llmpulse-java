

# CustomReportDateRange


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**type** | [**TypeEnum**](#TypeEnum) | rolling (the last range_days days) or previous_month (the previous calendar month) |  |
|**rangeDays** | **Integer** | Length of a rolling window; null for previous_month |  |
|**from** | **LocalDate** | First day of the window as of now (detail only) |  [optional] |
|**to** | **LocalDate** | Last day of the window as of now (detail only) |  [optional] |
|**label** | **String** | The window as the report shows it (detail only) |  [optional] |



## Enum: TypeEnum

| Name | Value |
|---- | -----|
| ROLLING | &quot;rolling&quot; |
| PREVIOUS_MONTH | &quot;previous_month&quot; |



