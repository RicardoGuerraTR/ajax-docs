---
title: Wrapping Node Text
page_title: Wrapping Node Text - RadTreeView
description: Check our Web Forms article about Wrapping Node Text.
slug: treeview/troubleshooting/wrapping-node-text
tags: wrapping,node,text
published: True
position: 0
---

# Wrapping Node Text

**RadTreeView** does not support text-wrapping by default. However, you can use one of the following approaches to accomplish the task. Add line breaks to the text of the **TreeNodes**:

````ASP.NET
<telerik:RadTreeNode runat="server" Text="Root<br>Node"/> 
````

To wrap all TreeNodes' Text add the following style to the page:

````CSS
#RadTreeView1 div {
	white-space: normal;
}
````

If the **TreeView** resides in a naming container, you can get the name of the div tag from the HTML output of the page.

Another way of applying the style is putting the style directly to the **TreeView** or **TreeNode** definition like this:

````ASP.NET
<telerik:RadTreeView RenderMode="Lightweight" ID="RadTreeView1" runat="server" Style="white-space: normal;" />

<telerik:RadTreeNode runat="server" Text="Root Node" style="white-space: normal;">
````

