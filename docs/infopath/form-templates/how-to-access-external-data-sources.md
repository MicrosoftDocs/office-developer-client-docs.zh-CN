---
title: 访问外部数据源
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
keywords:
- data connection classes [infopath 2007],secondary data sources [InfoPath 2007],data [InfoPath 2007], secondary,DataSource class [InfoPath 2007],accessing external data sources [InfoPath 2007],DataSourceCollection class [InfoPath 2007],DataConnectionCollection class [InfoPath 2007],DataConnection class [InfoPath 2007],InfoPath 2007, accessing external data,data [InfoPath 2007], external sources
localization_priority: Normal
ms.assetid: db7c2521-a1ad-4802-b398-79575d3d310a
description: 使用 InfoPath 表单模板时，可以编写代码以访问表单的辅助数据源和操作这些数据源所包含的数据。
ms.openlocfilehash: f6957c561231eef0e3e4df6deb09ae89f85afcc5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408311"
---
# <a name="access-external-data-sources"></a>访问外部数据源

使用 InfoPath 表单模板时，可以编写代码以访问表单的"辅助数据源"和操作这些数据源所包含的数据。 
  
每个辅助数据源均由使用 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 类实例化的对象代表，并且与从一些外部数据源（例如，数据库或 Web 服务查询）获得的存储数据相对应。这些数据源之所以被称为辅助数据源，是因为当用户保存 InfoPath 表单时，用户只保存主数据源中的数据，而不保存辅助数据源中的数据。与数据源的连接由使用"数据连接"类之一（例如 [WebServiceConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.aspx) 类，该类代表与 XML Web 服务的数据连接）实例化的对象代表。 
  
已实例化的 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 对象代表通过数据连接（从数据库或 Web 服务查询中）返回的 XML 数据的存储位置，并且“数据连接”类代表数据连接自身（使用“数据”**** 选项卡上的“数据连接”**** 命令来定义和命名）。 
  
通过结合使用 [DataSource](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.aspx) 类和 [DataSourceCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.aspx) 类，InfoPath 对象模型可支持对表单的辅助数据源进行访问。 
  
InfoPath 对象模型还提供了一组数据连接类，这些类包含有关表单所使用的数据连接的信息。
  
> [!NOTE]
> 在 Microsoft InfoPath 2003 中，数据连接称为"数据适配器"。 
  
数据连接有两种："查询连接"用于获取存储在辅助数据源中的数据。"提交连接"用于提交数据，例如，将数据提交到数据库或 Web 服务。提交的数据是从主数据源或辅助数据源中复制的。 
  
## <a name="overview-of-the-datasourcecollection-class"></a>DataSourceCollection 类概述

[DataSourceCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.aspx) 类提供了下列属性和方法，表单开发人员可以使用它们管理该表单包含的 [DataSourceCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.aspx) 对象实例。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.Count.aspx) 属性  <br/> |返回集合中包含的 **DataSource** 对象实例的数目。  <br/> |
|[GetEnumerator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.GetEnumerator.aspx) 方法  <br/> |返回可用于在集合中进行循环访问的 **IEnumerator**。  <br/> |
|[Item[Int32]](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.Item.aspx) 属性  <br/> |按照索引值返回一个对指定 **DataSource** 对象的引用。  <br/> |
|[Item[String]](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.Item.aspx) 属性  <br/> |按照名称返回一个对指定 **DataSource** 对象的引用。  <br/> |
   
## <a name="overview-of-the-datasource-class"></a>DataSource 类概述

[DataSourceCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSourceCollection.aspx) 类提供了下列方法和属性，表单开发人员可以使用它们与 InfoPath 辅助数据源进行交互。 
  
|**名称**|**说明**|
|:-----|:-----|
|[CreateNavigator](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.CreateNavigator.aspx) 方法  <br/> |返回用于访问和编辑数据源的 [XPathNavigator](https://msdn.microsoft.com/library/system.xml.xpath.xpathnavigator%28v=vs.110%29.aspx) 对象  <br/> |
|[QueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.QueryConnection.aspx) 属性  <br/> |获取一个对关联数据连接对象的引用。  <br/> 要对数据连接执行查询，并将返回的数据作为 XML 插入到与 **DataSource** 对象关联的 XML 节点中，请使用关联数据连接对象的 [Execute](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataConnection.Execute.aspx) 方法。  <br/> |
|[Name](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.Name.aspx) 属性  <br/> |获取 **DataSource** 对象的名称。  <br/> |
|[ReadOnly](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.ReadOnly.aspx) 属性  <br/> |获取一个值，指示数据源是否处于只读状态。  <br/> |
|[GetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.GetNamedNodeProperty.aspx) 方法  <br/> |获取指定 XML 节点的命名属性的值，该节点必须是主数据源中的 **nonattribute** 节点。  <br/> |
|[SetNamedNodeProperty](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataSource.SetNamedNodeProperty.aspx) 方法  <br/> |设置指定 XML 节点的命名属性的值，该节点必须是主数据源中的 **nonattribute** 节点。  <br/> |
   
## <a name="overview-of-the-data-connection-classes"></a>数据连接类概述

用于访问数据连接的类提供了通过连接到外部数据源检索和提交数据的不同属性和方法；与 **DataSource** 对象关联的数据连接取决于外部数据连接的类型。InfoPath 实现下列用于访问数据连接的类。 
  
|**名称**|**说明**|
|:-----|:-----|
|[AdoQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.aspx) 类  <br/> |查询 ADO/OLEDB 数据源；限于 Microsoft Access 和 Microsoft SQL Server。  <br/> |
|[AdoSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoSubmitConnection.aspx) 类  <br/> |提交到 ADO/OLEDB 数据源；限于 Microsoft Access 和 Microsoft SQL Server。  <br/> |
|[SharePointListRWQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharePointListRWQueryConnection.aspx) 类  <br/> |查询 SharePoint 列表或文档库。  <br/> |
|[SharePointListRWSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.SharePointListRWSubmitConnection.aspx) <br/> |提交到 SharePoint 列表或文档库。  <br/> |
|[WebServiceConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.WebServiceConnection.aspx) 类  <br/> |连接到 XML Web 服务。  <br/> |
|[FileQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileQueryConnection.aspx) 类  <br/> |查询 XML 文件。  <br/> |
|[FileSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FileSubmitConnection.aspx) 类  <br/> |提交到 XML 文件。  <br/> |
|[EmailSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.EmailSubmitConnection.aspx) 类  <br/> |将表单作为电子邮件的附件提交。  <br/> |
|[BdcQueryConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.BdcQueryConnection.aspx) 类  <br/> |在运行 SharePoint Foundation 2010 或 SharePoint Server 2010 的服务器上查询外部列表。  <br/> |
|[BdcSubmitConnection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.BdcSubmitConnection.aspx) 类  <br/> |提交到运行 SharePoint Foundation 2010 或 SharePoint Server 2010 的服务器上的外部列表。  <br/> |
   
## <a name="using-the-datasourcecollection-and-the-datasource-classes"></a>使用 DataSourceCollection 和 DataSource 类

**DataSourceCollection** 对象代表与一个表单模板关联的数据源的集合，可以通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataSources.aspx) 类的 [DataSources](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性来访问该对象。例如，如果创建一个从 Northwind 数据库的 Employees 表中检索数据的名为 Employees 的辅助数据源，可以使用 **DataSource** 对象设置一个对代表检索到的数据的 **DataSourceCollection** 对象的引用。 
  
在下面的代码示例中，辅助数据源的名称传递到 **DataSourceCollection** 类的 accessor 属性，该属性将返回一个对代表检索的 Employees 表数据的 **DataSource** 对象的引用。通过使用 **DataSource** 类的 **CreateNavigator** 方法访问 **XPathNavigator** 类的 **InnerXml** 属性，存储从辅助数据源中检索的数据的 XML 节点显示在一个消息框中。 
  
```cs
// Instantiate a variable to access the specified data source
// from the DataSourceCollection of the form.
DataSource myDataSource = 
   this.DataSources["Employees"];
// Display the XML data from the secondary data source.
MessageBox.Show("Data source data: " +
   myDataSource.CreateNavigator().InnerXml.ToString());
```

```vb
' Instantiate a variable to access the specified data source
' from the DataSourceCollection of the form.
Dim myDataSource As DataSource = _
   Me.DataSources("Employees")
' Display the XML data from the secondary data source.
MessageBox.Show("Data source data: " &amp; _
   myDataSource.CreateNavigator().InnerXml.ToString())
```

要操作辅助数据源中包含的数据，请使用 **DataSource** 类的 **CreateNavigator** 方法，返回对位于存储辅助数据的节点处的 **XPathNavigator** 对象的引用。 可以使用 **XPathNavigator** 类的属性或方法来操作数据。 有关详细信息，请参阅[使用 XPathNavigator 和 XPathNodeIterator 类](how-to-work-with-the-xpathnavigator-and-xpathnodeiterator-classes.md)。
  
## <a name="using-the-dataconnectioncollection-and-the-dataconnection-classes"></a>使用 DataConnectionCollection 和 DataConnection 类

[DataConnectionCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.DataConnectionCollection.aspx) 对象代表与一个表单模板关联的数据连接的集合，可以通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.DataConnections.aspx) 类的 **DataConnections** 属性来访问该对象。例如，如果创建一个从 Northwind 数据库的 Employees 表中检索数据的名为 Employees 的辅助数据源，可以使用与该表单模板关联的 **DataConnectionCollection** 对象来设置对 **DataConnection** 的引用，后者代表到数据库的连接。 
  
在下面的代码示例中，辅助数据源的名称传递到 **DataConnectionCollection** 类的 accessor 属性，在本例中，该属性会返回一个对代表到 Northwind 数据库的连接的 **ADOQueryConnection** 对象的引用。要使此引用正常工作，必须将返回的对象显式转换为 **ADOQueryConnection** 类型。 [ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.AdoQueryConnection.Connection.aspx) 接口的 **Connection** 属性用于在消息框中显示 ADO 连接字符串。 
  
```cs
// Instantiate a variable to access the specified data connection
// from the DataConnectionCollection of the form. 
// You must cast to the specific data connection type
// (ADOQueryConnection) before you can access the data connection.
ADOQueryConnection myADOConnection = 
   (ADOQueryConnection)this.DataConnections["Employees"];
// Display the connection information for the data connection.
MessageBox.Show("Connection string: " + myADOConnection.Connection);
```

```vb
' Instantiate a variable to access the specified data connection
' from the DataConnectionCollection of the form. 
' You must cast to the specific data connection type
' (ADOQueryConnection) before you can access the data connection.
Dim myADOConnection As ADOQueryConnection = _
   DirectCast(Me.DataConnections("Employees"), ADOQueryConnection)
' Display the connection information for the data connection.
MessageBox.Show("Connection string: " &amp; myADOConnection.Connection)
```

## <a name="see-also"></a>另请参阅



[创建使用 InfoPath Forms Services 的 InfoPath 表单模板](creating-infopath-form-templates-that-work-with-infopath-forms-services.md)

