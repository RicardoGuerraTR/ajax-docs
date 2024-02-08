---
title: Server-side Programming
page_title: Server-side Programming - RadProgressBar
description: Check our Web Forms article about Server-side Programming.
slug: progressbar/server-side-programming
tags: server-side,programming
published: True
position: 45
---

# Server-side Programming

You can configure the settings of **RadProgressBar** and create its elements in the code-behind via the Server-Side API of the control.

## RadProgressBar Public Properties and Methods

For a list with the server-side properties and methods of the control, see the [Server-Side API of the RadProgressBar class](/api/server/Telerik.Web.UI/RadProgressBar). You can also find it in the intellisense in Visual Studio.

## Creating and Configuring a ProgressBar From the Code-behind

**Example 1** shows a how you can use the server-side API of the ProgressBar, to create the control instance and configure some of the main	settings of the control. You can see the result from this code in **Figure 1**.
>caption Figure 1: A progress bar that is created and configured from the code-behind.

![programmatically-created-progress-bar](images/programmatically-created-progress-bar.png)

>caption Example 1: Configuring a progress bar on the server-side.


````C#
protected void Page_Init(object sender, EventArgs e)
{
	RadProgressBar progressBar = new RadProgressBar();

	progressBar.ID = "RadProgressBar1";
	progressBar.Width = 250;
	progressBar.BarType = Telerik.Web.UI.ProgressBarType.Percent;
	progressBar.Orientation = Telerik.Web.UI.ProgressBarOrientation.Horizontal;

	progressBar.MaxValue = 100;
	progressBar.Value = 33;
	progressBar.ShowLabel = true;
	progressBar.Skin = "Silk";

	Page.Controls.Add(progressBar);
}
````
````VB
Protected Sub Page_Init(sender As Object, e As EventArgs) Handles Me.Load
	Dim progressBar As New RadProgressBar()

	progressBar.ID = "RadProgressBar1"
	progressBar.Width = 250
	progressBar.BarType = Telerik.Web.UI.ProgressBarType.Percent
	progressBar.Orientation = Telerik.Web.UI.ProgressBarOrientation.Horizontal

	progressBar.MaxValue = 100
	progressBar.Value = 33
	progressBar.ShowLabel = True
	progressBar.Skin = "Silk"
	
	Page.Controls.Add(progressBar)
End Sub
````


## See Also

 * [Overview]({%slug progressbar/getting-started/overview%})

 * [Server-side Programming]({%slug progressbar/server-side-programming%})

 * [Types]({%slug progressbar/functionality/types%})
