---
title: Getting Started
page_title: Getting Started - RadListBox
description: Check our Web Forms article about Getting Started.
slug: listbox/getting-started
tags: getting,started
published: True
position: 4
---

# Getting Started with the Telerik WebForms ListBox

## 

This tutorial will show you how to:

* create two related RadListBox controls

* allow drag and drop between the above listbox controls

1. In a new AJAX Enabled Web Site, drop a RadListBox to the default form.

![Adding RadListBox from the ToolBox](images/listbox_toolbox.png "Adding RadListBox from the ToolBox")

2. From the [Smart Tag]({%slug listbox/design-time/smart-tag%}) click on the Add RadScriptManager link. It will automatically register the handler in the web.config file.

![Add Script Manager](images/listbox_add_radscriptmanager.png "Add Script Manager]")

![Handler Added](images/listbox_handler_added.png "Handler Added")

3. Click on the Build RadListBox link to open the [Item Builder]({%slug listbox/design-time/item-builder%}). Now use it to add several items:

![](images/listbox_item_builder.png)

4. Click on the **Add RadListBox** link. This will add another RadListBox on the page and will set the **TransferToID** property of the first listbox to the ID of the second listbox. This is needed for the [transfer]({%slug listbox/functionality/transfer%}) and [drag and drop]({%slug listbox/functionality/drag-and-drop%}) operations.

5. Set the **AllowReorder="True", AllowTransfer="True" and EnableDragAndDrop="True"** properties of the first RadListBox. This will show the necessary transfer and reorder buttons between the two listboxes so you will be able to reorder the items (move up and move down) and transfer the items (from the left to the right control and vice versa). In addition you will be able to use the mouse to drag and drop an item between the two listboxes or inside the RadListBox.

6. Select your favorite skin from the **Skin** dropdown to change the look and feel of the listbox.

7. Set the **Height** and **Width** properties of the listboxes so they look the same.

8. Run the project - now you can move the items up and down, left and right with the buttons. You can also drag and drop the items. In addition, you can move all items from right to left or vice versa with a single button click.

![Getting Started](images/listbox_getting_started.png "Getting Started")

9. To get the destination items iterate the **Items** collection of the second listbox using the foreach statement:


````C#
foreach (RadListBoxItem item in RadListBox2.Items)
{
    // do your stuff with the item
}			
````
````VB.NET
For Each item As RadListBoxItem In RadListBox2.Items
Next				
````

# See Also

 * [Overview]({%slug listbox/radlistbox-items/overview%})
