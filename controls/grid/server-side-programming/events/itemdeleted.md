---
title: ItemDeleted
page_title: ItemDeleted Event - RadGrid
description: Check our Web Forms article about ItemDeleted Event.
slug: grid/server-side-programming/events/itemdeleted
published: True
position: 50
---

# ItemDeleted Event

Fired when an automatic delete operation is executed.


### Event Parameters

* `(object)` **sender**

    * The control that fires the event

* `(GridDeletedEventArgs)` **e**

    * Event arguments 

        * `(int)` **e.AffectedRows**
            
            Gets the rows affected from the operation that changed the `RadGrid` data.

        * `(Exception)` **e.Exception**

            Gets the exception related with the operation. The property value will be 'null' if no exception occured durring the operation.
            
        * `(bool)` **e.ExceptionHandled**

            Gets or sets a value which if set to 'true' and exception was thrown will cause the `RadGrid` to skip throwing the exception and will let the user handle it.

        * `(GridEditableItem)` **e.Item**

            Gets the `GridEditableItem` which caused the event.

## Attaching the event

In the Markup

````ASP.NET
<telerik:RadGrid ID="RadGrid1" runat="server" OnItemDeleted="RadGrid1_ItemDeleted">
</telerik:RadGrid>
````

In the Code behind

````C#
protected void Page_Init(object sender, EventArgs e)
{
    RadGrid1.ItemDeleted += RadGrid1_ItemDeleted;
}
````
````VB
Protected Sub Page_Init(sender As Object, e As EventArgs) Handles Me.Init
    AddHandler RadGrid1.ItemDeleted, AddressOf RadGrid1_ItemDeleted
End Sub
````

The event handler

````C#
protected void RadGrid1_ItemDeleted(object sender, GridDeletedEventArgs e)
{
    int affectedRows = e.AffectedRows;
    Exception exception = e.Exception;
    bool exceptionHandled = e.ExceptionHandled;
    GridEditableItem item = e.Item;
}
````
````VB
Protected Sub RadGrid1_ItemDeleted(ByVal sender As Object, ByVal e As GridDeletedEventArgs)
    Dim affectedRows As Integer = e.AffectedRows
    Dim exception As Exception = e.Exception
    Dim exceptionHandled As Boolean = e.ExceptionHandled
    Dim item As GridEditableItem = e.Item
End Sub
````

## See Also

* [Telerik RadGrid Event Sequence]({%slug grid/control-lifecycle/event-sequence%})


