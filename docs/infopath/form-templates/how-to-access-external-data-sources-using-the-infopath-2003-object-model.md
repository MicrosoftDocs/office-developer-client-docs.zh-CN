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
ms.openlocfilehash: 569f029b412328f4d49e3079eaf207dc1556fc4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431678"
---
# <a name="access-external-data-sources-using-the-infopath-2003-object-model"></a><span data-ttu-id="2df8a-104">使用 InfoPath 2003 对象模型访问外部数据源</span><span class="sxs-lookup"><span data-stu-id="2df8a-104">Access External Data Sources Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="2df8a-105">如果 InfoPath 表单模板使用了 InfoPath 2003 兼容对象模型，则在使用此表单模板时，可以编写代码以访问表单的辅助数据源和处理它们包含的数据。</span><span class="sxs-lookup"><span data-stu-id="2df8a-105">When working with an InfoPath form template that uses the InfoPath 2003 compatible object model, you can write code to access the form's secondary data sources and manipulate the data that they contain.</span></span>
  
<span data-ttu-id="2df8a-p101">每个辅助数据源均由使用 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口实例化的对象表示，并且与从一些外部数据源（例如，数据库或 Web 服务查询）获得的存储数据相对应。这些数据源之所以被称为辅助数据源，是因为当用户保存 InfoPath 表单时，用户只保存主数据源中的数据，而不保存辅助数据源中的数据。与数据源的连接由使用"数据适配器"接口之一（例如 [WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) 接口，该接口表示与 XML Web 服务的数据连接）实例化的对象表示。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p101">Each secondary data source is represented by an object instantiated using the [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) interface, and corresponds to stored data, obtained from some external source of data, such as a database or a Web Service query. These data sources are referred to as secondary because when the user saves an InfoPath form, the user is saving the data only in the main data source, not the data in the secondary data sources. The connection to a data source is represented by an object instantiated using one of the "data adapter" interfaces, such as the [WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) interface, which represents a data connection to an XML Web Service.</span></span> 
  
<span data-ttu-id="2df8a-109">实例化的 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 对象表示由数据连接（指向数据库或 Web 服务查询）返回的 XML 数据的存储，而数据适配器表示数据连接本身。</span><span class="sxs-lookup"><span data-stu-id="2df8a-109">The instantiated [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) object represents the storage of XML data returned by a data connection (to a database or Web Service query), and the data adapter represents the data connection itself.</span></span> 
  
<span data-ttu-id="2df8a-110">通过结合使用 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口和 [DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) 接口，InfoPath 对象模型可支持对表单的辅助数据源进行访问。</span><span class="sxs-lookup"><span data-stu-id="2df8a-110">The InfoPath object model supports access to a form's secondary data sources through the use of the [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) interface in association with the [DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) interface.</span></span> 
  
<span data-ttu-id="2df8a-111">InfoPath 对象模型也提供一组数据适配器对象，这些对象包含有关表单所使用的数据连接的信息。</span><span class="sxs-lookup"><span data-stu-id="2df8a-111">The InfoPath object model also provides a set of data adapter objects, containing information about the data connections used by the form.</span></span> 
  
<span data-ttu-id="2df8a-p102">有两种类型的数据适配器：查询适配器和提交适配器。查询适配器用于获取随后存储到辅助数据源中的数据，而提交适配器用于提交数据，例如提交到数据库或 Web 服务。提交的数据通过主或辅助数据源复制。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p102">There are two kinds of data adapters: Query adapters and Submit adapters. Query adapters are used to obtain the data that is then stored in a secondary data source whereas Submit adapters are used to submit data, to a database or Web service, for example. The submitted data is copied from the main or secondary data sources.</span></span> 
  
## <a name="overview-of-the-dataobjectscollection-interface"></a><span data-ttu-id="2df8a-115">DataObjectsCollection 接口概述</span><span class="sxs-lookup"><span data-stu-id="2df8a-115">Overview of the DataObjectsCollection Interface</span></span>

<span data-ttu-id="2df8a-116">[DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) 接口提供了下列属性和方法，表单开发人员可以将其用于管理该表单包含的 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 实例。</span><span class="sxs-lookup"><span data-stu-id="2df8a-116">The [DataObjectsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjectsCollection.aspx) interface provides the following properties and methods, which form developers can use to manage the [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) instances that the form contains.</span></span> 
  
|<span data-ttu-id="2df8a-117">**名称**</span><span class="sxs-lookup"><span data-stu-id="2df8a-117">**Name**</span></span>|<span data-ttu-id="2df8a-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="2df8a-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2df8a-119">[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Count.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2df8a-119">[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Count.aspx) property</span></span>  <br/> |<span data-ttu-id="2df8a-120">返回集合中包含的 **DataSourceObject** 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="2df8a-120">Returns a count of the number of **DataSourceObject** instances contained in the collection.</span></span>  <br/> |
|<span data-ttu-id="2df8a-121">[GetEnumerator](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.GetEnumerator.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2df8a-121">[GetEnumerator](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.GetEnumerator.aspx) method</span></span>  <br/> |<span data-ttu-id="2df8a-122">返回可用于在集合中进行循环访问的 **IEnumerator**。</span><span class="sxs-lookup"><span data-stu-id="2df8a-122">Returns an **IEnumerator** that can be used to iterate through the collection.</span></span>  <br/> |
|<span data-ttu-id="2df8a-123">[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Item.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2df8a-123">[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObjects.Item.aspx) property</span></span>  <br/> |<span data-ttu-id="2df8a-124">返回一个对指定 **DataSourceObject** 实例的引用。</span><span class="sxs-lookup"><span data-stu-id="2df8a-124">Returns a reference to the specified **DataSourceObject** instance.</span></span>  <br/> |
   
## <a name="overview-of-the-datasourceobject-interface"></a><span data-ttu-id="2df8a-125">DataSourceObject 接口概述</span><span class="sxs-lookup"><span data-stu-id="2df8a-125">Overview of the DataSourceObject Interface</span></span>

<span data-ttu-id="2df8a-126">[DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 接口提供了下列方法和属性，表单开发人员可以将其用于与 InfoPath 辅助数据源进行交互。</span><span class="sxs-lookup"><span data-stu-id="2df8a-126">The [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) interface provides the following method and properties, which form developers can use to interact with an InfoPath secondary data source.</span></span> 
  
|<span data-ttu-id="2df8a-127">**名称**</span><span class="sxs-lookup"><span data-stu-id="2df8a-127">**Name**</span></span>|<span data-ttu-id="2df8a-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="2df8a-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2df8a-129">[Query](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Query.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="2df8a-129">[Query](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Query.aspx) method</span></span>  <br/> |<span data-ttu-id="2df8a-130">对数据适配器执行查询并将返回的数据作为 XML 插入与 **DataSourceObject** 关联的 XML 文档对象模型 (DOM)。</span><span class="sxs-lookup"><span data-stu-id="2df8a-130">Executes the query on the data adapter and inserts the returned data as XML into the XML Document Object Model (DOM) associated with the **DataSourceObject**.</span></span>  <br/> |
|<span data-ttu-id="2df8a-131">[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.DOM.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2df8a-131">[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.DOM.aspx) property</span></span>  <br/> |<span data-ttu-id="2df8a-132">返回一个对使用 **DataSourceObject** 存储和操作数据的 XML DOM 的引用。</span><span class="sxs-lookup"><span data-stu-id="2df8a-132">Returns a reference to the XML DOM used to store and manipulate data using the **DataSourceObject**.</span></span>  <br/> |
|<span data-ttu-id="2df8a-133">[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Name.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2df8a-133">[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.Name.aspx) property</span></span>  <br/> |<span data-ttu-id="2df8a-134">返回表示 **DataSourceObject** 对象的名称的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2df8a-134">Returns a string value indicating the name of the **DataSourceObject**.</span></span>  <br/> |
|<span data-ttu-id="2df8a-135">[QueryAdapter](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.QueryAdapter.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="2df8a-135">[QueryAdapter](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataObject.QueryAdapter.aspx) property</span></span>  <br/> |<span data-ttu-id="2df8a-136">返回一个对关联数据适配器对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2df8a-136">Returns a reference to the associated data adapter object.</span></span>  <br/> |
   
## <a name="overview-of-the-data-adapter-interfaces"></a><span data-ttu-id="2df8a-137">数据适配器接口概述</span><span class="sxs-lookup"><span data-stu-id="2df8a-137">Overview of the Data Adapter Interfaces</span></span>

<span data-ttu-id="2df8a-p103">用于访问数据适配器的接口提供了通过连接到外部数据源来检索和提交数据的不同属性和方法；与 [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) 对象关联的数据适配器取决于外部数据连接的类型。InfoPath 实现下列用于访问数据适配器的接口。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p103">The interfaces for accessing data adapters provide different properties and methods that retrieve and submit data through connections to external data sources; the data adapter that is associated with a [DataSourceObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataSourceObject.aspx) object is dependent on the type of external data connection. InfoPath implements the following interfaces for accessing data adapters.</span></span> 
  
|<span data-ttu-id="2df8a-140">**名称**</span><span class="sxs-lookup"><span data-stu-id="2df8a-140">**Name**</span></span>|<span data-ttu-id="2df8a-141">**说明**</span><span class="sxs-lookup"><span data-stu-id="2df8a-141">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2df8a-142">[ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapterObject.aspx) 接口</span><span class="sxs-lookup"><span data-stu-id="2df8a-142">[ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapterObject.aspx) interface</span></span>  <br/> |<span data-ttu-id="2df8a-143">连接到 ADO/OLEDB 数据源；限于 Microsoft Access 和 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="2df8a-143">Connects to ADO/OLEDB data sources; limited to Microsoft Access and Microsoft SQL Server™.</span></span>  <br/> |
|<span data-ttu-id="2df8a-144">[SharepointListAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SharepointListAdapterObject.aspx) 接口</span><span class="sxs-lookup"><span data-stu-id="2df8a-144">[SharepointListAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.SharepointListAdapterObject.aspx) interface</span></span>  <br/> |<span data-ttu-id="2df8a-145">连接 SharePoint 列表或文档库。</span><span class="sxs-lookup"><span data-stu-id="2df8a-145">Connects to a SharePoint list or document library.</span></span>  <br/> |
|<span data-ttu-id="2df8a-146">[WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) 接口</span><span class="sxs-lookup"><span data-stu-id="2df8a-146">[WebServiceAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WebServiceAdapterObject.aspx) interface</span></span>  <br/> |<span data-ttu-id="2df8a-147">连接 XML Web 服务。</span><span class="sxs-lookup"><span data-stu-id="2df8a-147">Connects to XML Web services.</span></span>  <br/> |
|<span data-ttu-id="2df8a-148">[XMLFileAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLFileAdapterObject.aspx) 对象</span><span class="sxs-lookup"><span data-stu-id="2df8a-148">[XMLFileAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLFileAdapterObject.aspx) object</span></span>  <br/> |<span data-ttu-id="2df8a-149">连接 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="2df8a-149">Connects to an XML file.</span></span>  <br/> |
   
## <a name="using-the-datasourceobjects-and-the-datasourceobject-interfaces"></a><span data-ttu-id="2df8a-150">使用 DataSourceObjects 和 DataSourceObject 接口</span><span class="sxs-lookup"><span data-stu-id="2df8a-150">Using the DataSourceObjects and the DataSourceObject Interfaces</span></span>

<span data-ttu-id="2df8a-p104">可通过 **XDocument** 接口的 [DataObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataObjects.aspx) 属性访问 [DataSourceObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 集合。例如，如果创建一个从 Northwind Traders Microsoft Access 数据库的 Employees 表中检索数据的名为 Employees 的辅助数据源，可以使用 **DataSourceObjects** 集合设置一个对表示检索到的数据的 **DataObject** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p104">The **DataSourceObjects** collection is accessed through the [DataObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataObjects.aspx) property of the [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) interface. For example, if you create a secondary data source named Employees that retrieves data from the Employees table in the Northwind Traders Microsoft Access database, you can use the **DataSourceObjects** collection to set a reference to a **DataObject** object that represents the retrieved data.</span></span> 
  
<span data-ttu-id="2df8a-p105">在下列代码示例中，辅助数据源的名称传递到 **DataObjectsCollection** 接口的 accessor 属性，该属性将返回一个对 **DataSourceObject** 对象的引用。通过使用 **DataSourceObject** 接口的 **DOM** 属性访问 XML DOM 的 **xml** 属性的方法，在消息框中显示辅助数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p105">In the following code sample, the name of the secondary data source is passed to the accessor property of the **DataObjectsCollection** interface, which returns a reference to the **DataSourceObject** object. The data from the secondary data source is displayed in a message box by using the **DOM** property of the **DataSourceObject** interface to access the **xml** property of the XML DOM.</span></span> 
  
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

<span data-ttu-id="2df8a-p106">若要操作包含在辅助数据源中的数据，可使用 **DataSourceObject** 接口的 **DOM** 属性返回一个对包含这些数据的 XML DOM 的引用。获得 XML DOM 的引用后，可以使用它的任何属性或方法操作其中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p106">To manipulate the data that is contained in a secondary data source, use the **DOM** property of the **DataSourceObject** interface to return a reference to the XML DOM containing the data. When you have the reference to the XML DOM, you can use any of its properties or methods to manipulate the data that it contains.</span></span> 
  
## <a name="using-the-dataadapterscollection-and-the-dataadapterobject-interfaces"></a><span data-ttu-id="2df8a-157">使用 DataAdaptersCollection 和 DataAdapterObject 接口</span><span class="sxs-lookup"><span data-stu-id="2df8a-157">Using the DataAdaptersCollection and the DataAdapterObject Interfaces</span></span>

<span data-ttu-id="2df8a-p107">可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataAdaptersCollection.aspx) 接口的 [DataAdapters](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataAdapters.aspx) 属性访问 **DataAdaptersCollection** 接口。例如，如果创建从 Northwind Traders Microsoft Access 数据库的 Employees 表中检索数据且名为 Employees 的辅助数据源，可以使用 **DataAdapterObjects** 集合设置一个对表示数据库连接的 **DataAdapterObject** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p107">The [DataAdaptersCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataAdaptersCollection.aspx) interface is accessed through the [DataAdapters](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataAdapters.aspx) property of the **XDocument** interface. For example, if you create a secondary data source named Employees that retrieves data from the Employees table in the Northwind Traders Microsoft Access database, you can use the **DataAdapterObjects** collection to set a reference to the **DataAdapterObject** that represents the connection to the database.</span></span> 
  
<span data-ttu-id="2df8a-p108">在下列代码示例中，辅助数据源的名称被传递给 **DataAdaptersCollection** 的 accessor 属性，在本例中，该属性会返回一个对表示到 Northwind Microsoft Access 数据库的连接的 **ADOAdapterObject** 实例的引用。要使该引用正常工作，必须将被返回的对象显式转换为 **ADOAdapterObject**。 [ADOAdapterObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapter2.Connection.aspx) 接口的 **Connection** 属性用于在消息框中显示 ADO 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="2df8a-p108">In the following code sample, the name of the secondary data source is passed to the accessor property of the **DataAdaptersCollection**, which, in this case, returns a reference to an instance of the **ADOAdapterObject** that represents the connection to the Northwind Microsoft Access database. For this to work properly, you must explicitly cast the object being returned as an **ADOAdapterObject**. The [Connection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ADOAdapter2.Connection.aspx) property of the **ADOAdapterObject** interface is used to display the ADO connection string in a message box.</span></span> 
  
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


