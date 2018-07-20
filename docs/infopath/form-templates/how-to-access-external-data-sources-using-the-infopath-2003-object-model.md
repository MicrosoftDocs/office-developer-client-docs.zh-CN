---
title: 使用 InfoPath 2003 对象模型访问外部数据源
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- data sources [infopath 2007], accessing with infopath 2003 object model,InfoPath 2003-compatible form templates, accessing external data
localization_priority: Normal
ms.assetid: 9fd9ca47-abf1-48dd-8668-dfee27161793
description: 如果 InfoPath 表单模板使用了 InfoPath 2003 兼容对象模型，则在使用此表单模板时，可以编写代码以访问表单的辅助数据源和处理它们包含的数据。
ms.openlocfilehash: cf06cdc6a02eba855442cdab4c3c698ed3f4425f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773978"
---
# <a name="access-external-data-sources-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型访问外部数据源

如果 InfoPath 表单模板使用了 InfoPath 2003 兼容对象模型，则在使用此表单模板时，可以编写代码以访问表单的辅助数据源和处理它们包含的数据。
  
每个辅助数据源均由使用 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口实例化的对象表示，并且与从一些外部数据源（例如，数据库或 Web 服务查询）获得的存储数据相对应。这些数据源之所以被称为辅助数据源，是因为当用户保存 InfoPath 表单时，用户只保存主数据源中的数据，而不保存辅助数据源中的数据。与数据源的连接由使用"数据适配器"接口之一（例如 [WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) 接口，该接口表示与 XML Web 服务的数据连接）实例化的对象表示。 
  
实例化的 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 对象表示由数据连接（指向数据库或 Web 服务查询）返回的 XML 数据的存储，而数据适配器表示数据连接本身。 
  
通过结合使用 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口和 [DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) 接口，InfoPath 对象模型可支持对表单的辅助数据源进行访问。 
  
InfoPath 对象模型也提供一组数据适配器对象，这些对象包含有关表单所使用的数据连接的信息。 
  
有两种类型的数据适配器：查询适配器和提交适配器。查询适配器用于获取随后存储到辅助数据源中的数据，而提交适配器用于提交数据，例如提交到数据库或 Web 服务。提交的数据通过主或辅助数据源复制。 
  
## <a name="overview-of-the-dataobjectscollection-interface"></a>DataObjectsCollection 接口概述

[DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) 接口提供了下列属性和方法，表单开发人员可以将其用于管理该表单包含的 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 实例。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Count.aspx) 属性  <br/> |返回集合中包含的 **DataSourceObject** 实例的数目。  <br/> |
|[GetEnumerator](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.GetEnumerator.aspx) 方法  <br/> |返回可用于在集合中进行循环访问的 **IEnumerator**。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Item.aspx) 属性  <br/> |返回一个对指定 **DataSourceObject** 实例的引用。  <br/> |
   
## <a name="overview-of-the-datasourceobject-interface"></a>DataSourceObject 接口概述

[DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口提供了下列方法和属性，表单开发人员可以将其用于与 InfoPath 辅助数据源进行交互。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Query](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Query.aspx) 方法  <br/> |对数据适配器执行查询并将返回的数据作为 XML 插入与 **DataSourceObject** 关联的 XML 文档对象模型 (DOM)。  <br/> |
|[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.DOM.aspx) 属性  <br/> |返回一个对使用 **DataSourceObject** 存储和操作数据的 XML DOM 的引用。  <br/> |
|[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Name.aspx) 属性  <br/> |返回表示 **DataSourceObject** 对象的名称的字符串值。  <br/> |
|[QueryAdapter](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.QueryAdapter.aspx) 属性  <br/> |返回一个对关联数据适配器对象的引用。  <br/> |
   
## <a name="overview-of-the-data-adapter-interfaces"></a>数据适配器接口概述

用于访问数据适配器的接口提供了通过连接到外部数据源来检索和提交数据的不同属性和方法；与 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 对象关联的数据适配器取决于外部数据连接的类型。InfoPath 实现下列用于访问数据适配器的接口。 
  
|**名称**|**说明**|
|:-----|:-----|
|[ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapterObject.aspx) 接口  <br/> |连接到 ADO/OLEDB 数据源；限于 Microsoft Access 和 Microsoft SQL Server。  <br/> |
|[SharepointListAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SharepointListAdapterObject.aspx) 接口  <br/> |连接 SharePoint 列表或文档库。  <br/> |
|[WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) 接口  <br/> |连接 XML Web 服务。  <br/> |
|[XMLFileAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLFileAdapterObject.aspx) 对象  <br/> |连接 XML 文件。  <br/> |
   
## <a name="using-the-datasourceobjects-and-the-datasourceobject-interfaces"></a>使用 DataSourceObjects 和 DataSourceObject 接口

可通过 **XDocument** 接口的 [DataObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataObjects.aspx) 属性访问 [DataSourceObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 集合。例如，如果创建一个从 Northwind Traders Microsoft Access 数据库的 Employees 表中检索数据的名为 Employees 的辅助数据源，可以使用 **DataSourceObjects** 集合设置一个对表示检索到的数据的 **DataObject** 对象的引用。 
  
在下列代码示例中，辅助数据源的名称传递到 **DataObjectsCollection** 接口的 accessor 属性，该属性将返回一个对 **DataSourceObject** 对象的引用。通过使用 **DataSourceObject** 接口的 **DOM** 属性访问 XML DOM 的 **xml** 属性的方法，在消息框中显示辅助数据源中的数据。 
  
```cs
public void CTRL1_5_OnClick(DocActionEvent e)
{
   // Instantiate a variable to access the specified data object
   // from the DataObjectsCollection of the form.
   // You must explicitly cast to the DataSourceObject type 
   // before you can access the data object.
   DataSourceObject myDataObject = 
      thisXDocument.DataObjects["Employees"] as DataSourceObject;
   // Display the data from the secondary data source using the 
   // XML DOM.
   thisXDocument.UI.Alert("Data Adapter: " + myDataObject.DOM.xml);
}
```

```vb
Public Sub CTRL1_5_OnClick(ByVal e As DocActionEvent)
   ' Instantiate a variable to access the specified data object
   ' from the DataObjectsCollection of the form.
   Dim myDataObject As DataSourceObject = _
      thisXDocument.DataObjects("Employees")
   ' Display the data from the secondary data source using the 
   ' XML DOM.
   thisXDocument.UI.Alert("Data Adapter: " + myDataObject.DOM.xml)
End Sub
```

若要操作包含在辅助数据源中的数据，可使用 **DataSourceObject** 接口的 **DOM** 属性返回一个对包含这些数据的 XML DOM 的引用。获得 XML DOM 的引用后，可以使用它的任何属性或方法操作其中包含的数据。 
  
## <a name="using-the-dataadapterscollection-and-the-dataadapterobject-interfaces"></a>使用 DataAdaptersCollection 和 DataAdapterObject 接口

可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataAdaptersCollection.aspx) 接口的 [DataAdapters](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataAdapters.aspx) 属性访问 **DataAdaptersCollection** 接口。例如，如果创建从 Northwind Traders Microsoft Access 数据库的 Employees 表中检索数据且名为 Employees 的辅助数据源，可以使用 **DataAdapterObjects** 集合设置一个对表示数据库连接的 **DataAdapterObject** 对象的引用。 
  
在下列代码示例中，辅助数据源的名称被传递给 **DataAdaptersCollection** 的 accessor 属性，在本例中，该属性会返回一个对表示到 Northwind Microsoft Access 数据库的连接的 **ADOAdapterObject** 实例的引用。要使该引用正常工作，必须将被返回的对象显式转换为 **ADOAdapterObject**。 [ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapter2.Connection.aspx) 接口的 **Connection** 属性用于在消息框中显示 ADO 连接字符串。 
  
```cs
public void CTRL1_5_OnClick(DocActionEvent e)
{
   // Instantiate a variable to access the specified data object
   // from the DataAdaptersCollection of the form. 
   // You must explicitly cast to the specific adapter type
   // (ADOAdapterObject) before you can access the data adapter.
   ADOAdapterObject myADOAdapter = 
      thisXDocument.DataAdapters["Employees"] as ADOAdapterObject;
   // Display the connection information for the data adapter.
   thisXDocument.UI.Alert("Data Adapter: " + myADOAdapter.Connection);
}
```

```vb
Public Sub CTRL1_5_OnClick(ByVal e As DocActionEvent)
   ' Instantiate a variable to access the specified data object. 
   ' You must explicitly cast to the specific adapter type
   ' (ADOAdapterObject) before you can access the data adapter.
   Dim myADOAdapter As ADOAdapterObject = _
      thisXDocument.DataAdapters("Employees")
   ' Display the connection information for the data adapter.
   thisXDocument.UI.Alert("Data Adapter: " + myADOAdapter.Connection)
End Sub
```


