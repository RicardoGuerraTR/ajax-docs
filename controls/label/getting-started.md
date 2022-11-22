---
title: Getting Started
page_title: Getting Started
description: Check our Web Forms article about Getting Started.
slug: label/getting-started
tags: getting,started
published: True
position: 1
---

# Getting Started with the Telerik WebForms Label


This article describes a sample scenario where **RadLabel** is used with a **RadDatePicker** control.


1. Add a **RadLabel** control to the page.
    ````ASP.NET
<telerik:RadLabel runat="server" ID="RadLabel1" Text="sample text">
</telerik:RadLabel>
````


1. Next, place a **RadDatePicker** control on the page.

    ````ASP.NET
<telerik:RadDatePicker RenderMode="Lightweight" runat="server" ID="RadDatePicker1">
</telerik:RadDatePicker>
````


1. Set the **AssociatedControlID** property of **RadLabel** to be the same as the **ID** of the **RadDatePicker**. After that when you click on the **Label** the **DateInput** will be focused.

    ````ASP.NET
<telerik:RadLabel runat="server" ID="RadLabel1" Text="sample text" AssociatedControlID="RadDatePicker1">
</telerik:RadLabel>
````


1. *Optional* If you prefer the label to be on a different line you can add a `<br>` element after the label.

    ````ASP.NET
<telerik:RadLabel runat="server" ID="RadLabel1" Text="sample text" AssociatedControlID="RadDatePicker1">
</telerik:RadLabel>
<br />
````


1. *Optional* In addition you can use an image instead of text for the label. To do this you should place an image inside the **RadLabel** tags.

    ````ASP.NET
<telerik:RadLabel runat="server" ID="RadLabel1" AssociatedControlID="RadDatePicker1">
    <img src="/images/myImage.png" alt="" />
</telerik:RadLabel>
<br />
````


1. The complete markup looks like below:

    ````ASP.NET
<telerik:RadLabel runat="server" ID="RadLabel1" AssociatedControlID="RadDatePicker1">
    <img src="/images/myImage.png" alt="" />
</telerik:RadLabel>
<br />
<telerik:RadDatePicker RenderMode="Lightweight" runat="server" ID="RadDatePicker1"></telerik:RadDatePicker>
````


