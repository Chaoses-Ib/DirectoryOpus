# DPI

The **DPI** object is a helper object that provides a number of methods and properties relating to the system DPI setting. For example, you can use it to convert a pixel width into one scaled for the current system DPI. The **DPI** object is returned via the **[DOpus](dopus.md).DPI** property.

| Property Name | Return Type | Description |
| --- | --- | --- |
| dpi | *int* | Returns the system DPI setting as a “dpi value” (e.g. 96, 192). |
| factor | *int* | Returns the DPI settings as a “scale factor” (e.g. 100, 125, 200). |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Divide | \<int:value\> | *int* | Divides the provided size by the system DPI; e.g. if the system DPI was set to 150%, **DPI.Divide(60)** would return **40.** |
| Scale | \<int:value\> | *int* | Scales the provided size by the system DPI; e.g. if the system DPI was set to 200%, **DPI.Scale(75)** would return **150**. |

