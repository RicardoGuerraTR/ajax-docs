---
title: Overview
page_title: Getting Started Overview - RadProgressBar
description: Check our Web Forms article about Overview.
slug: progressbar/getting-started/overview
tags: overview
published: True
position: 0
---

# Getting Started Overview

The following tutorial demonstrates how you can add a simple **RadProgressBar** control with a preset value displayed in percent. The end result will be similar to	**Figure 1**:

>caption Figure 1: A RadProgressBar with a predefined percentage value.

![progress-bar-getting-started-1](images/progress-bar-getting-started-1.png)

Add a **ScriptManager** control on a Web Form.

Add a **RadProgressBar** control on this AJAX-enabled Web Form:

>caption Example 1: Declaration of a **RadProgressBar** control.

````ASP.NET
<telerik:RadProgressBar RenderMode="Lightweight" runat="server" ID="RadProgressBar1">
</telerik:RadProgressBar>
````

Set some of the properties of the ProgressBar like **BarType**, **Value**, **MaxValue** and **Orientation**	to configure the progress bar in the desired way.

>caption Example 2: The progress bar now is horizontally oriented, configured with the desired value in percent.

````ASP.NET	
<telerik:RadProgressBar RenderMode="Lightweight" runat="server" ID="RadProgressBar1" 
	BarType="Percent" MaxValue="100" Value="33" Width="250" 
	Orientation="Horizontal" ShowLabel="true" Skin="Silk">
</telerik:RadProgressBar>
````

## See Also

 * [RadProgressBar Elements Structure]({%slug progressbar/getting-started/element-structure%})

 * [Types]({%slug progressbar/functionality/types%})

 * [RadProgressBar Server-Side Programming]({%slug progressbar/server-side-programming%})
