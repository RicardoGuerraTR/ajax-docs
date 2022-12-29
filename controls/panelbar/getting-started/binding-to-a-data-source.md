---
title: Binding to a Data Source
page_title: Binding to a Data Source - RadPanelBar
description: Check our Web Forms article about Binding to a Data Source.
slug: panelbar/getting-started/binding-to-a-data-source
tags: binding,to,a,data,source
published: True
position: 3
---

# Binding to a Data Source



## 

This tutorial will show how to bind the Telerik Accordion component to an **AccessDataSource**:

1. Locate the "Nwind.mdb" file that appears in the "Live Demos\App_Data" sub-folder of the folder where you installed RadControls "for ASP.NET Ajax".

2. Drag this file ("Northwind.mdf") to the "App_Data" folder in the Solution Explorer for your project:![Nwind MDB](images/panelbar_nwindmdb.png)

3. Add the following connection string in the web config file under the connection string section:![Connection String](images/panelbar_connection_string.png)

4. Drag a **RadPanelBar** component from the toolbox onto your Web page. The **RadPanelBar** [Smart Tag]({%slug panelbar/design-time/smart-tag%}) should appear automatically:![PanelBar Tasks](images/panelbar_gettingstarted1.png)

5. In the **RadPanelBar** Smart Tag, use the **Skin** drop-down to change the [skin]({%slug panelbar/appearance-and-styling/skins%}) for the **RadPanelBar** to "Vista":![Vista Skin](images/panelbar_skinvista.png)

6. Still in the Smart Tag, open the **Choose Data Source** drop-down and select **New Data Source**:
	![New Data Source](images/panelbar_newdatasource.png)

7. The Data Source Configuration Wizard appears. In the Select a DataSource Type screen, specify an **SqlDataSource** and click **OK.**![Choose A DataSourcecType](images/panelbar_chooseadatasourcetype.png)

8. In the **Choose your Data Connection** screen, click the **Browse** button, and select the "NorthwindConnectionString". Then choose **Next** to continue:
	![Choose A Database](images/panelbar_chooseadatabase.png)

9. In the **Configure the Select Statement** screen, choose **Specify columns from a table or view**.

10. In the **Name** drop-down, select the "Employees" table.

11. In the **Columns** panel, Select the "EmployeeID", "FirstName", and "ReportsTo" fields. Then choose **Next** to continue:![Configure Select](images/panelbar_configureselect.png)

12. Click the **Test Query** button to see the data. Then click **Finish** to exit the Configure Data Source Wizard:![Query Test](images/panelbar_testquery.png)

13. In the Properties pane for the **RadPanelBar** component,

	* Set the **DataFieldId** property to "EmployeeID".

	* Set the **DataFieldParentId** property to "ReportsTo".

	* Set the **DataTextField** property to "FirstName":
	![Data Fields](images/panelbar_datafields.png)

14. Run the application. The panel bar has a single root level item (for the one record with a null value in the "ReportsTo" field). When you expand this item, you can see level 1 items for every record that had Andrew's ID in the "ReportsTo" field. You can expand the item labelled "Steven" to see the level 2 items for records that had Steven's ID in the "ReportsTo" field:
	
![Bound PanelBar](images/panelbar_bound.png)

# See Also

 * [Data Binding Overview]({%slug panelbar/data-binding/overview%})

 * [Getting Started Overview]({%slug panelbar/getting-started/overview%})
