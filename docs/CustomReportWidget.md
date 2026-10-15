

# CustomReportWidget


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**key** | **String** |  |  |
|**label** | **String** |  |  |
|**kind** | [**KindEnum**](#KindEnum) |  |  |
|**width** | [**WidthEnum**](#WidthEnum) |  |  |
|**available** | **Boolean** | false when the widget&#39;s data source (web analytics, agent analytics, owned media) is not connected |  |
|**data** | **Map&lt;String, Object&gt;** | Shaped by kind. timeseries: series [{ name, color, points [{ date, value }] }]. donut: slices [{ name, value, color }]. bar: bars [{ label, value, color }]. kpi_grid: values and changes (null unless the report compares with the previous period). table: rows, one object per row. Null when the widget is not available. |  [optional] |



## Enum: KindEnum

| Name | Value |
|---- | -----|
| KPI_GRID | &quot;kpi_grid&quot; |
| TIMESERIES | &quot;timeseries&quot; |
| DONUT | &quot;donut&quot; |
| BAR | &quot;bar&quot; |
| TABLE | &quot;table&quot; |



## Enum: WidthEnum

| Name | Value |
|---- | -----|
| HALF | &quot;half&quot; |
| FULL | &quot;full&quot; |



