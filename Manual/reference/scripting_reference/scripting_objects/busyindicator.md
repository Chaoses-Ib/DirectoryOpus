# BusyIndicator

A **BusyIndicator** object lets you control the breadcrumbs bar busy indicator from your script.

![](/Manual/images/media/throbbler.png)

By default a busy indicator simply indicates that something is happening; it can also be used to indicate the progress of a job (percentage complete from 0% to 100%). The user can click the spinning circle to see a description of the jobs that are running, and each job can optionally allow the user to abort it by displaying an *Abort* link they can click.

**BusyIndicator** objects are created using the **[DOpusFactory](dopusfactory.md).BusyIndicator** method. The basic steps for using one in your script are:

1.  Create the object by calling **DOpus.Create.BusyIndicator()**.
2.  Optionally set the **abort** property to **True** to enable user aborting.
3.  Call the **Init** method to initialize and display the busy indicator.
4.  Call the **Update** method when needed to update the progress or explanatory text.
5.  Poll the **abort** property to check for user abort if desired.
6.  Call the **Destroy** method to remove the busy indicator when the job is complete.

| Property Name | Return Type | Description |
| --- | --- | --- |
| abort | *bool* | Before the **Init** method has been called, you can set this property to **True** to enable abort by the user (as shown above).  <br />After **Init** has been called, this property will return **True** if the user has clicked the *Abort* link.  <br />The **abort** property does not change if the lister or tab your **BusyIndicator** is associated with closes. If you need to stop when that happens then you must check for it separately, typically by testing the result of the **Update** method. |

| Method Name | **Arguments** | Return Type | Description |
| --- | --- | --- | --- |
| Destroy | *none* | *bool* | Removes the busy indicator from display and destroys its internal data structures. The **BusyIndicator** object itself can be re-used by calling the **Init** method again.  <br />Returns boolean success. Failure usually means the lister or tab was closed. |
| Hide | *none* | *bool* | Removes the busy indicator from display, but does not destroy its internal data. The indicator can be re-displayed by calling the **Show** method.  <br />Returns boolean success. Failure usually means the lister or tab was closed. |
| Init | \<object:window\>  <br />\<string:description\>  <br />\<bool:visible\> | *bool* | Initializes a **BusyIndicator** object and optionally displays it.  <br />The **window** parameter specifies the **[Lister](lister.md)** or **[Tab](tab.md)** object that the indicator is to be attached to. Using a **Tab** is usually best.  <br />The optional **description** parameter lets you specify a text string that is displayed to the user when they click the spinning circle.  <br />The optional **visible** parameter lets you make the indicator visible immediately by passing **True**. Alternatively, call the **Show** method to make the indicator visible.  <br />Returns boolean success. Failure usually means the lister or tab was closed or invalid. |
| Show | *none* | *bool* | Displays the busy indicator.  <br />Returns boolean success. Failure usually means the lister or tab was closed. |
| Update | \<string:description\>  <br />\<int:percentage\> | *bool* | Updates the busy indicator.  <br />The **description** parameter lets you specify a new description string.  <br />The optional **percentage** parameter lets you specify a new progress bar percentage from 0 to 100. If no **percentage** is specified, and none was set by a previous call, the progress bar displays an animation indicating something is happening without a known percentage.  <br />Returns boolean success. Failure usually means the lister or tab was closed. |

