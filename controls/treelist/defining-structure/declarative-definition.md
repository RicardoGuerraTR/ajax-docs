---
title: Declarative Definition
page_title: Declarative Definition - RadTreeList
description: Check our Web Forms article about Declarative Definition.
slug: treelist/defining-structure/declarative-definition
tags: declarative,definition
published: True
position: 0
---

# Declarative Definition



## 

**RadTreeList** enables you to bind to self-hierarchical data structures and display them. You can define the control completely in mark-up. Following is a description of the key points in **RadTreeList** declarative definition:

1. You need to specify the id of the data source that the **RadTreeList** control will be bound to (through the **DataSourceID** property) and the **ParentDataKeyNames** and **DataKeyNames** which define the hierarchical relations in the control.

1. Then you should choose between:
	* using the feature for automatically generating columns(**AutoGenerateColumns = "true"**, the default value) which will create a column for each field in the specified data source. The auto-generated columns will be displayed in the same order as the fields in the data source.
	* creating the columns through mark up or dynamically at runtime. In this case they will be displayed in the order you declare them.
1. Once you are ready to display your data, you can customize the additional features of the control, like paging, sorting and item selection.

1. The last touch to the control would be customizing its appearance - you can set its **Skin** property to point to one of our built-in Skins or a custom one. Also, you can use the styling properties exposed in order to access and modify the look of only certain parts of the control. These are: **PagerStyle**, **ItemStyle**, **AlternatingItemStyle**, **HeaderStyle**,**SelectedItemStyle**.

````C#
<telerik:RadTreeList RenderMode="Lightweight" ID="RadTreeList1" runat="server" DataSourceID="SqlDataSource1"
	ParentDataKeyNames="ReportsTo" DataKeyNames="EmployeeID" AutoGenerateColumns="false"
	AllowPaging="true" PageSize="7" AllowMultiItemSelection="true" Skin="Vista">
	<ClientSettings Selecting-AllowItemSelection="true" />
	<Columns>
		<telerik:TreeListBoundColumn DataField="ReportsTo" UniqueName="ReportsTo" HeaderText="Reports To" />
		<telerik:TreeListBoundColumn DataField="EmployeeID" UniqueName="EmployeeID" HeaderText="Employee ID" />
		<telerik:TreeListTemplateColumn UniqueName="Name" HeaderText="Name">
			<HeaderTemplate>
				Full Name
			</HeaderTemplate>
			<ItemTemplate>
				<%# Eval("FirstName")%>&nbsp;<%# Eval("LastName")%>
			</ItemTemplate>
			<HeaderStyle Width="200px" />
			<ItemStyle HorizontalAlign="Center" />
		</telerik:TreeListTemplateColumn>
		<telerik:TreeListBoundColumn DataField="BirthDate" UniqueName="BirthDate" DataFormatString="{0:dd/MM/yy}" 
			HeaderText="Birth Date" />
		<telerik:TreeListCheckBoxColumn UniqueName="CheckBoxColumn" />
	</Columns>
</telerik:RadTreeList>
<asp:SqlDataSource ID="SqlDataSource1" ConnectionString="<%$ ConnectionStrings:NorthwindConnectionString %>"
	ProviderName="System.Data.SqlClient" SelectCommand="SELECT EmployeeID, LastName, FirstName, Title, BirthDate, ReportsTo FROM Employees"
	runat="server">
</asp:SqlDataSource>
````


