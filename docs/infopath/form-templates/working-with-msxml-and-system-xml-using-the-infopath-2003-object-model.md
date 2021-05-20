---
title: 使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, using msxml5,MSXML5 [InfoPath 2007],MSXML5 script [InfoPath 2007],InfoPath 2007, using MSXML5
localization_priority: Normal
ms.assetid: f7a0cac5-26f9-49ed-b52c-0240ef0c9d38
description: 使用 InfoPath 2003 对象模型的表单模板项目在内部利用 Microsoft XML Core Services (MSXML) 来处理 XML。在托管代码中，使用由 .NET Framework 类库中的 System.Xml 命名空间所提供的 XML 支持通常更加容易。由于性质决定，MSXML 和 System.Xml 不能交换对象，因此当需要在 InfoPath 与其他托管代码之间传递 XML 数据时，需要转换 XML 数据。使用本主题中的技术，您可以将 System.Xml 对象中的 XML 数据与 InfoPath 表单代码进行交换。
ms.openlocfilehash: c56939a0cf03b5de6466de37013e154529afd1ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437397"
---
# <a name="working-with-msxml-and-systemxml-using-the-infopath-2003-object-model"></a><span data-ttu-id="19ec7-107">使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml</span><span class="sxs-lookup"><span data-stu-id="19ec7-107">Working with MSXML and System.Xml Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="19ec7-p102">使用 InfoPath 2003 对象模型的表单模板项目在内部利用 Microsoft XML Core Services (MSXML) 来处理 XML。在托管代码中，使用由 .NET Framework 类库中的 **System.Xml** 命名空间所提供的 XML 支持通常更加容易。由于性质决定，MSXML 和 **System.Xml** 不能交换对象，因此当需要在 InfoPath 与其他托管代码之间传递 XML 数据时，需要转换 XML 数据。使用本主题中的技术，您可以将 **System.Xml** 对象中的 XML 数据与 InfoPath 表单代码进行交换。</span><span class="sxs-lookup"><span data-stu-id="19ec7-p102">Form template projects that work with the InfoPath 2003 object model use Microsoft XML Core Services (MSXML) internally to work with XML. In managed code, it is often easier to use the XML support provided by the **System.Xml** namespace in the .NET Framework class library. MSXML and **System.Xml** cannot exchange objects natively, so whenever you need to pass XML data between InfoPath and other managed code, XML data needs to be converted. You can exchange XML data from **System.Xml** objects with InfoPath form code by using the techniques in this topic.</span></span> 
  
<span data-ttu-id="19ec7-112">若要在使用 InfoPath 2003 对象模型的托管代码项目中使用 **System.Xml** 命名空间的成员，必须在 Visual Studio 2012 内的“**添加引用**”对话框中的“**.NET**”选项卡上添加对 **System.Xml** 的引用。</span><span class="sxs-lookup"><span data-stu-id="19ec7-112">To use members of the **System.Xml** namespace in a managed code project that uses the InfoPath 2003 object model, you must add a reference to **System.Xml** on the **.NET** tab of the **Add Reference** dialog box in Visual Studio 2012.</span></span> 
  
 <span data-ttu-id="19ec7-113">**备注**</span><span class="sxs-lookup"><span data-stu-id="19ec7-113">**Notes**</span></span>
  
- <span data-ttu-id="19ec7-114">若需查看有关 MSXML 的参考信息，请参阅 MSXML SDK。</span><span class="sxs-lookup"><span data-stu-id="19ec7-114">To view reference information about MSXML, see the MSXML SDK.</span></span>
    
- <span data-ttu-id="19ec7-115">由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 命名空间封装的 MSXML 对象模型的成员无法分配给托管代码表单模板的表单代码中的委托。</span><span class="sxs-lookup"><span data-stu-id="19ec7-115">Members of the MSXML object model that are wrapped by the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace cannot be assigned to delegates in the form code of managed-code form templates.</span></span> 
    
- <span data-ttu-id="19ec7-p103">If you update the code of your form template to use the object model provided by members of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace, **System.Xml** is used natively. However, when doing so, you must manually convert all of your code to use the new object model. To convert your form template to use the new object model, in the **Programming** category of the **Form Options** dialog box, click **Upgrade OM**.</span><span class="sxs-lookup"><span data-stu-id="19ec7-p103">If you update the code of your form template to use the object model provided by members of the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace, **System.Xml** is used natively. However, when doing so, you must manually convert all of your code to use the new object model. To convert your form template to use the new object model, in the **Programming** category of the **Form Options** dialog box, click **Upgrade OM**.</span></span>
    
## <a name="loading-an-entire-xml-document-object-model-dom-from-systemxml"></a><span data-ttu-id="19ec7-119">从 System.Xml 中加载整个 XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="19ec7-119">Loading an Entire XML Document Object Model (DOM) from System.Xml</span></span>

<span data-ttu-id="19ec7-120">下面的代码示例演示如何使用 InfoPath **CreateDOM** 方法和由 [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.CreateDOM.aspx) 命名空间成员封装的 Microsoft XML Core Services 成员，从 [System.Xml](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) 代码中加载整个 XML DOM。</span><span class="sxs-lookup"><span data-stu-id="19ec7-120">The following code sample demonstrates how to load an entire XML DOM from **System.Xml** code using the InfoPath [CreateDOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.CreateDOM.aspx) method and the members of Microsoft XML Core Services that are wrapped by members of the [Microsoft.Office.Interop.InfoPath.SemiTrust](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.aspx) namespace.</span></span> 
  
<span data-ttu-id="19ec7-p104">The following examples require a **using** or **Imports** directive for **System.Xml** in the declarations section of the form code module. Additionally, because the **Load** method of the **XmlDocument** class requires **System.Security.Permissions.FileIOPermission**, you must configure the security level of the form template as **Full Trust** using the **Security and Trust** category of the **Form Options** dialog box.</span><span class="sxs-lookup"><span data-stu-id="19ec7-p104">The following examples require a **using** or **Imports** directive for **System.Xml** in the declarations section of the form code module. Additionally, because the **Load** method of the **XmlDocument** class requires **System.Security.Permissions.FileIOPermission**, you must configure the security level of the form template as **Full Trust** using the **Security and Trust** category of the **Form Options** dialog box.</span></span> 
  
```cs
// Create a System.Xml XmlDocument and load an XML file.
XmlDocument doc = new XmlDocument();
doc.Load("c:\\temp\\MyFile.xml");
// Create an MSXML DOM object.
IXMLDOMDocument newDoc = thisXDocument.CreateDOM();
// Load the DOM with the XML from the System.XML object.
newDoc.loadXML(doc.DocumentElement.OuterXml);
```

```vb
' Create a System.Xml XmlDocument and load an XML file.
Dim doc As XmlDocument = New XmlDocument()
doc.Load("c:\temp\MyFile.xml");
' Create an MSXML DOM object.
Dim newDoc As IXMLDOMDocument = thisXDocument.CreateDOM()
' Load the DOM with the XML from the System.XML object.
newDoc.loadXML(doc.DocumentElement.OuterXml)
```

## <a name="loading-a-single-node-from-systemxml"></a><span data-ttu-id="19ec7-123">从 System.Xml 中加载单个节点</span><span class="sxs-lookup"><span data-stu-id="19ec7-123">Loading a Single Node from System.Xml</span></span>

<span data-ttu-id="19ec7-p105">下面的代码示例显示一个函数，该函数演示如何使用封装的 MSXML **createNode** 方法从 **System.Xml**. **XmlElement** 中克隆单个节点。</span><span class="sxs-lookup"><span data-stu-id="19ec7-p105">The following code sample shows a function that demonstrates how to clone a single node from a **System.Xml**. **XmlElement** using the wrapped MSXML **createNode** method.</span></span> 
  
<span data-ttu-id="19ec7-126">下面的示例要求在表单代码模块的声明部分对 **System.Xml** 使用 **using** 或 **Imports** 指令。</span><span class="sxs-lookup"><span data-stu-id="19ec7-126">The following examples require a **using** or **Imports** directive for **System.Xml** in the declarations section of the form code module.</span></span> 
  
```cs
// This function takes a System.Xml XmlElement object and 
// an MSXML IXMLDOMDocument object, and returns an MSXML 
// IXMLDOMNode object that is a copy of the XmlElement object.
public IXMLDOMNode CloneSystemXmlElementToMsxml(
   XmlElement systemXmlElement, IXMLDOMDocument msxmlDocument)
{
   IXMLDOMNode msxmlResultNode;
   // Create a new element from the MSXML DOM using the same 
   // namespace as the XmlElement.
   msxmlResultNode = msxmlDocument.createNode(
      DOMNodeType.NODE_ELEMENT, 
      systemXmlElement.Name, 
      systemXmlElement.NamespaceURI);
   // Set the element's value.
   msxmlResultNode.text = systemXmlElement.Value.ToString();
   return msxmlResultNode;
}
```

```vb
' This function takes a System.Xml XmlElement object and 
' an MSXML IXMLDOMDocument object, and returns an MSXML 
' IXMLDOMNode object that is a copy of the XmlElement object.
Public Function CloneSystemXmlElementToMsxml(_
   XmlElement systemXmlElement, _
   IXMLDOMDocument msxmlDocument) As IXMLDOMNode
   Dim msxmlResultNode As IXMLDOMNode
   ' Create a new element from the MSXML DOM using the same 
   ' namespace as the XmlElement.
   msxmlResultNode = msxmlDocument.createNode(_
      DOMNodeType.NODE_ELEMENT, _
      systemXmlElement.Name, _
      systemXmlElement.NamespaceURI)
   ' Set the element's value.
   msxmlResultNode.text = systemXmlElement.Value.ToString()
   Return msxmlResultNode
End Function
```


