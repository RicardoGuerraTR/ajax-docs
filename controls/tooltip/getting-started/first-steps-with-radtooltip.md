---
title: First Steps with RadToolTip
page_title: First Steps with RadToolTip - RadTooltip
description: Check our Web Forms article about First Steps with RadToolTip.
slug: tooltip/getting-started/first-steps-with-radtooltip
tags: first,steps,with,radtooltip
published: True
position: 0
---

# First Steps with RadToolTip



The following tutorial demonstrates how **RadToolTip** is used to provide a custom tooltip for a single element.


![](images/tooltip-gettingstarted001.png)

1. In a new AJAX-Enabled Web Application, add a **HyperLink** control from the Standard tab to the default web page.

1. Set the **Text** property to "Telerik Web Site" and the **NavigateUrl** to "https://www.telerik.com".

1. Drop a **RadToolTip** control from the ToolBox to the default web page.

1. Set the RadToolTip **TargetControlID** property to the ID property of the HyperLink.

1. Set the **Position** property to be **BottomCenter**.

1. Set the **Title** property to "Telerik Site Link".

1. Set the **Text** property to "Click here to navigate to the Telerik Web Site".

1. Set the **Skin** property to **Telerik**.

1. Press **F5** to run the application. Run the mouse over the HyperLink to view the tooltip.

Example 1 - Creating RadTooltip in the aspx page

````ASPX
<telerik:RadScriptManager ID="RadScriptManager1" runat="server" />
<asp:HyperLink ID="HyperLink1" runat="server" Text="Telerik Web Site" NavigateUrl="https://www.telerik.com"></asp:HyperLink>
<telerik:RadToolTip ID="RadToolTip1" runat="server" TargetControlID="HyperLink1" Position="BottomCenter"
    Skin="Telerik" Title="Telerik Site Link" Width="200px" Height="60px">
    <contenttemplate>
        Click here to navigate to the Telerik Web Site
    </contenttemplate>
</telerik:RadToolTip>
````

Example 2 - Dynamic creation

````C#
    protected void Page_Load(object sender, EventArgs e)
    {
        Button button = new Button();
        button.ID = "Button1";
        button.Text = "Click me";
        button.ToolTip = "This is a tooltip";

        RadToolTip tooltip = new RadToolTip();
        tooltip.TargetControlID = "Button1";
        tooltip.Text = "This is a tooltip";
        tooltip.BackColor = Color.Yellow;
        tooltip.ForeColor = Color.Red;

        this.Form.Controls.Add(button);
        this.Form.Controls.Add(tooltip);
    }
````
````VB.NET
Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs)
    Dim button As Button = New Button()
    button.ID = "Button1"
    button.Text = "Click me"
    button.ToolTip = "This is a tooltip"
    Dim tooltip As RadToolTip = New RadToolTip()
    tooltip.TargetControlID = "Button1"
    tooltip.Text = "This is a tooltip"
    tooltip.BackColor = Color.Yellow
    tooltip.ForeColor = Color.Red
    Me.Form.Controls.Add(button)
    Me.Form.Controls.Add(tooltip)
End Sub
````

# See Also

 * [FIrst Steps with RadToolTipManager]({%slug tooltip/getting-started/first-steps-with-radtooltipmanager%})
