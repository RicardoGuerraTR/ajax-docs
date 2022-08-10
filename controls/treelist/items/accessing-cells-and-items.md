---
title: Accessing Cells and Items
page_title: Accessing Cells and Items - RadTreeList
description: Check our Web Forms article about Accessing Cells and Items.
slug: treelist/items/accessing-cells-and-items
tags: accessing,cells,and,items
published: True
position: 1
---

# Accessing Cells and Items



There are various ways to access the different items of the RadTreeList control.The most important ones are shown below.

## Accessing TreeListDataItems and their values

You can access the RadTreeList data items either using the item events of the control(ItemCreated, ItemDataBound, ItemCommand) or by looping through its Items collection when it is available.



````C#
//e is the event argument object
if (e.Item is TreeListDataItem)
{
	TreeListDataItem item = e.Item as TreeListDataItem;
}
````
````VB.NET
If TypeOf e.Item Is TreeListDataItem Then
	Dim item As TreeListDataItem = CType(e.Item, TreeListDataItem)
End If
````




````C#
foreach (TreeListDataItem item in RadTreeList1.Items)
{
	//perform some action with the data item
}
````
````VB.NET
For Each item As TreeListDataItem In RadTreeList1.Items
	'perform some action with the data item
Next
````


Once you get hold of a certain data item, you can access its cells by using the **UniqueName**	property of the column that the cell belongs to.



````C#
TableCell cell = dataItem["ColumnUniqueName"]; //where dataItem is an object of type TreeListDataItem
````
````VB.NET
Dim cell As TableCell = dataItem("ColumnUniqueName") 'where dataItem is an object of type TreeListDataItem
````


With bound columns you can use the **Text**property to get the value of the cell.



````C#
string itemValue = cell.Text;
````
````VB.NET
Dim itemValue As String = cell.Text
````


For values in **TreeListTemplateColumns** you will need to find the control in the treelist cell (either using the **FindControl()** method or the	**Controls** collection of the cell) and extract its value.



````C#
string title = (dataItem["ColumnUniqueName"].FindControl("Label1") as Label).Text;
````
````VB.NET
Dim title As String = CType(dataItem("ColumnUniqueName").FindControl("Label1"), Label).Text
````


In case you want to access a checkbox in a TreeListCheckBoxColumn, you will be able to get hold of it through the	cell's **Controls** collection.



````C#
CheckBox chk = dataItem["Qualifies"].Controls[0] as CheckBox;
````
````VB.NET
Dim chk As CheckBox = CType(dataItem("Qualifies").Controls(0), CheckBox)
````


If you need to get hold of the expand/collapse button in the treelist data item you can do so by using FindControl()	having in mind that the button id is **"ExpandCollapseButton"**:



````C#
if (dataItem.FindControl("ExpandCollapseButton") != null)
{
	Button btn = dataItem.FindControl("ExpandCollapseButton") as Button;
}
````
````VB.NET
If Not dataItem.FindControl("ExpandCollapseButton") Is Nothing Then
	Dim btn As Button = CType(dataItem.FindControl("ExpandCollapseButton"), Button)
End If
````


## Accessing the TreeListHeaderItem

You can use the **ItemCreated** and **ItemDataBound** events Of RadTreeListto get hold of the header.



````C#
if (e.Item is TreeListHeaderItem)
{
	TreeListHeaderItem header = e.Item as TreeListHeaderItem;
	TableCell headerCell = header["ColumnUniqueName"] as TableCell;
}
````
````VB.NET
If TypeOf e.Item Is TreeListHeaderItem Then
	Dim header As TreeListHeaderItem = TryCast(e.Item, TreeListHeaderItem)

End If
````


Same as with the TreeListDataItem, you can access the separate cells by using the **UniqueName** of the column in question.



````C#
TableCell headerCell = header["ColumnUniqueName"] as TableCell;
````
````VB.NET
Dim headerCell As TableCell = CType(header("ColumnUniqueName"), TableCell)
````


## Accessing the TreeListPagerItem

You can use the same approach to get hold of the pager as for the header:



````C#
if (e.Item is TreeListPagerItem)
{
	TreeListPagerItem pager = e.Item as TreeListPagerItem;
	pager.PagerContentCell.BackColor = System.Drawing.Color.AliceBlue;
}
````
````VB.NET
If TypeOf e.Item Is TreeListPagerItem Then
	Dim pager As TreeListPagerItem = CType(e.Item, TreeListPagerItem)
	pager.PagerContentCell.BackColor = System.Drawing.Color.AliceBlue
End If
````


## Accessing the TreeListDetailTemplateItem

The **ItemCreated** and **ItemDataBound** events are the place where you can access the TreeListDetailTemplateItem as well.



````C#
if (e.Item is TreeListDetailTemplateItem)
{
	TreeListDetailTemplateItem detailItem = e.Item as TreeListDetailTemplateItem;
	Label lbl = detailItem.FindControl("Label1") as Label;
}
````
````VB.NET
If TypeOf e.Item Is TreeListDetailTemplateItem Then
	Dim detailItem As TreeListDetailTemplateItem = TryCast(e.Item, TreeListDetailTemplateItem)
End If
````


After that you can use the **FindControl()** method to get reference to the controls specified in the template.



````C#
Label lbl = detailItem.FindControl("Label1") as Label;
````
````VB.NET
Dim lbl As Label = CType(detailItem.FindControl("Label1"), Label)
````


## Accessing the TreeListNoRecordsItem

You can access the item rendered when the treelist is bound to an empty data source again the same way:



````C#
if (e.Item is TreeListNoRecordsItem)
{
	TreeListNoRecordsItem noRecordsItem = e.Item as TreeListNoRecordsItem;
}
````
````VB.NET
If TypeOf e.Item Is TreeListNoRecordsItem Then
	Dim detailItem As TreeListNoRecordsItem = TryCast(e.Item, TreeListNoRecordsItem)
End If
````

## Finding a TreeListDataItem by Key Value

**RadTreeList** provides a method to search for an existing item via the data key values of the underlying record. This method supports both key and parent key parameters.



````C#
protected void Button1_Click(object sender, EventArgs e)
{
		TreeListDataItem item = RadTreeList1.FindItemByKeyValue("RecordID", 3);
}
````
````VB.NET
Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
	Dim item As TreeListDataItem = RadTreeList1.FindItemByKeyValue("RecordID", 3)
End Sub
````

If no items are found, the method returns null. In case there are multiple records matching the parameters, the method will return only the first item.

# See Also

 * [Overview]({%slug treelist/items/overview%})
