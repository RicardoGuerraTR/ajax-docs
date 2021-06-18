---
title: Click To Open
page_title: Click To Open - RadMenu
description: Check our Web Forms article about Click To Open.
slug: menu/functionality/click-to-open
tags: click,to,open
published: True
position: 6
---

# Click To Open

## ClickToOpen

You can use the **ClickToOpen** property to specify that menu items do not expand when the mouse hovers over them until the user clicks the menu with the mouse. When **ClickToOpen** is **True**, the menu does not expand until the user clicks on a root item, at which point the root item expands. Once clicked, the menu expands and collapses as normal, until the user clicks again (either on a menu item or outside the menu). The **ExpandDelay** property controls the time, in milliseconds, after the user first clicks the menu until the menu item expands. The **CollapseDelay** property controls the time, in milliseconds, after the user clicks a second time until the menu items all collapse.

## Example:

````ASP.NET
<telerik:RadMenu RenderMode="Lightweight" ID="RadMenu1" runat="server" ClickToOpen="True">
````

By default The ClickToOpen functionality is applicable only for the Root items of the RadMenu. To apply the same functionality for the sub-items, a custom implementation is required. An idea how to achieve that you can find in the [Apply ClickToOpen functionality for sub-items of RadMenu](https://www.telerik.com/support/kb/aspnet-ajax/menu/details/apply-clicktoopen-functionality-for-sub-items-of-radmenu) knowledge base article.

