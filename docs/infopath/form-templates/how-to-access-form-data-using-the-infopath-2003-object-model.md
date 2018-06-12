---
title: 使用 InfoPath 2003 对象模型访问表单数据
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- xdocument interface [infopath 2007],InfoPath 2003-compatible form templates, accessing form data,XDocumentsCollection interface [InfoPath 2007]
localization_priority: Normal
ms.assetid: e0731014-f454-4417-9f90-19f3387f5776
description: 若要扩展 InfoPath 表单的功能，通常必须以编程方式访问与表单的基础 XML 文档有关的信息、访问 XML 文档所包含的数据或对 XML 文档执行某些操作。通过结合使用 XDocument 接口和 XDocumentsCollection 接口，InfoPath 对象模型可支持对表单的基础 XML 文档进行访问和操作。
ms.openlocfilehash: 24e9abc8ce7327ab94b3608f1279c0f0d381ea83
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773982"
---
# <a name="access-form-data-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型访问表单数据

若要扩展 InfoPath 表单的功能，通常必须以编程方式访问与表单的基础 XML 文档有关的信息、访问 XML 文档所包含的数据或对 XML 文档执行某些操作。通过结合使用 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 接口和 [XDocumentsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocumentsCollection.aspx) 接口，InfoPath 对象模型可支持对表单的基础 XML 文档进行访问和操作。 
  
**XDocument** 接口是 InfoPath 对象模型中最有用的类型之一，因为它提供许多属性、方法和事件，不仅能与表单的基础 XML 文档进行交互，而且能够执行 InfoPath 用户界面中的许多可用的操作。在使用 InfoPath 2003 兼容对象模型创建的托管代码项目中，将在项目的表单代码中包含事件处理程序的类的  **** 方法中，自动定义一个名为  `thisXDocument` 的 `_StartUp` 类型的变量。您可以在表单代码中使用  `thisXDocument` 变量访问 **XDocument** 接口及其成员。 
  
## <a name="overview-of-the-xdocumentscollection-interface"></a>XDocumentsCollection 接口概述

**XDocumentsCollection** 接口提供下列方法和属性，表单开发人员可以使用它们管理集合所包含的 **XDocument** 对象。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Close](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.Close.aspx) 方法  <br/> |关闭指定的表单。  <br/> |
|[New](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.New.aspx) 方法  <br/> |基于现有的表单创建新表单。  <br/> |
|[NewFromSolution](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.NewFromSolution.aspx) 方法  <br/> |基于现有的表单模板创建新表单。  <br/> |
|[NewFromSolutionWithData](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.NewFromSolutionWithData.aspx) 方法  <br/> |使用指定的 XML 数据和表单模板创建新的 InfoPath 表单。  <br/> |
|[Open](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.Open.aspx) 方法  <br/> |打开指定的表单。  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.Count.aspx) 属性  <br/> |返回集合中包含的 **XDocument** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocuments2.Item.aspx) 属性  <br/> |返回对指定 **XDocument** 对象的引用。  <br/> |
   
## <a name="overview-of-the-xdocument-interface"></a>XDocument 接口概述

**XDocument** 接口提供下列方法和属性，表单开发人员可以使用它们与表单的基础 XML 文档进行交互，并对该文档执行操作。 
  
|**名称**|**说明**|
|:-----|:-----|
|[GetDataVariable](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.GetDataVariable.aspx) 方法  <br/> |返回指定数据变量的字符串值。  <br/> |
|[GetDOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.GetDOM.aspx) 方法  <br/> |返回对与指定 **DataObject** 对象关联的 XML 文档对象模型 (DOM) 的引用。  <br/> |
|[ImportFile](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.ImportFile.aspx) 方法  <br/> |使用当前打开的表单导入（或合并）指定的表单。  <br/> |
|[PrintOut](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.PrintOut.aspx) 方法  <br/> |打印表单的当前视图。  <br/> |
|[Query](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Query.aspx) 方法  <br/> |从表单的相关数据适配器中检索数据。  <br/> |
|[Save](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Save.aspx) 方法  <br/> |保存当前打开的表单。  <br/> |
|[SaveAs](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.SaveAs.aspx) 方法  <br/> |用指定的名称保存当前打开的表单。  <br/> |
|[SetDataVariable](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.SetDataVariable.aspx) 方法  <br/> |设置指定数据变量的值。  <br/> |
|[Submit](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Submit.aspx) 方法  <br/> |按照在设计模式中建立的提交操作提交表单。  <br/> |
|[DataObjects](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DataObjects.aspx) 属性  <br/> |返回一个对 **DataObjects** 集合的引用。  <br/> |
|[DOM](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.DOM.aspx) 属性  <br/> |返回对以表单的源 XML 数据填充的 XML DOM 的引用。  <br/> |
|[Errors](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Errors.aspx) 属性  <br/> |返回一个对 **Errors** 集合的引用。  <br/> |
|[Extension](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Extension.aspx) 属性  <br/> |返回对特定对象的引用，该对象表示表单代码文件中包含的所有函数和变量。  <br/> |
|[IsDirty](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsDirty.aspx) 属性  <br/> |返回指示表单中的数据是否已更改的 **Boolean** 值。  <br/> |
|[IsDOMReadOnly](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsDOMReadOnly.aspx) 属性  <br/> |返回指示是否将 XML DOM 设置为只读的 **Boolean** 值。  <br/> |
|[IsNew](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsNew.aspx) 属性  <br/> |返回指示表单创建后是否保存过的 **Boolean** 值。  <br/> |
|[IsReadOnly](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsReadOnly.aspx) 属性  <br/> |返回指示表单是否处于只读模式的 **Boolean** 值。  <br/> |
|[IsSigned](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.IsSigned.aspx) 属性  <br/> |返回指示表单是否经过数字签名的 **Boolean** 值。  <br/> |
|[Language](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Language.aspx) 属性  <br/> |指定或返回表单所使用的语言的字符串值。  <br/> |
|[QueryAdapter](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.QueryAdapter.aspx) 属性  <br/> |返回对数据适配器对象的引用。  <br/> |
|[Solution](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.Solution.aspx) 属性  <br/> |返回对 **Solution** 对象的引用。  <br/> |
|[UI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.UI.aspx) 属性  <br/> |返回对 **UI** 对象的引用。  <br/> |
|[URI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.URI.aspx) 属性  <br/> |返回包含表单的统一资源标识符 (URI) 的字符串值。  <br/> |
|[View](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.View.aspx) 属性  <br/> |返回对 **View** 对象的引用。  <br/> |
|[ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.ViewInfos.aspx) 属性  <br/> |返回对 **ViewInfos** 集合的引用。  <br/> |
   
## <a name="using-the-xdocuments-collection-and-the-xdocument-interfaces"></a>使用 XDocuments 集合和 XDocument 接口

可通过 **Application** 接口的 [XDocuments](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._Application2.XDocuments.aspx) 属性访问 [XDocumentsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Application.aspx) 接口。在使用 InfoPath 2003 兼容对象模型创建的托管代码项目中，您可以使用在项目的表单代码中的  **** 方法中实例化了的  `thisApplication` 变量来访问 `_StartUp` 接口。下列代码行将创建一个引用当前项目的 **XDocumentsCollection** 接口的变量。 
  
```cs
XDocumentsCollection xdocs;
xdocs = thisApplication.XDocuments;
// Write code here to work with the XDocumentsCollection.
```

```vb
Dim xdocs As XDocumentsCollection
xdocs = thisApplication.XDocuments
' Write code here to work with the XDocumentsCollection.
```

在使用 InfoPath 2003 兼容对象模型创建的托管代码项目中，您可以使用在项目的表单代码中的  **** 方法中实例化了的  `thisXDocument` 变量来访问 `StartUp` 接口。下列代码行使用  `thisXDocument` 变量来访问当前项目的 **XDocument** 接口，以便在警告消息中显示当前打开表单的 URI。 
  
```cs
thisXDocument.UI.Alert(thisXDocument.URI);
```

```vb
thisXDocument.UI.Alert(thisXDocument.URI)
```

> [!NOTE]
> [!注释] 使用 **XDocument** 接口访问表单的基础 XML 文档时，实际上是在访问与当前打开表单相关联的 XML 文档。 
  
**XDocument** 接口的一个关键属性是 **DOM** 属性。该属性返回以表单的源 XML 数据填充的 XML DOM 的引用。使用 **DOM** 属性时，可以使用 XML DOM 支持的任何属性和方法。例如，下列代码使用 XML DOM 的 **xml** 属性来返回并显示表单的基础 XML 文档的全部内容。 
  
```cs
string xmldoc;
xmldoc = thisXDocument.DOM.xml;
// Display xml.
thisXDocument.UI.Alert(xmldoc);
```

```vb
Dim xmldoc As String
xmldoc = thisXDocument.DOM.xml
' Display xml.
thisXDocument.UI.Alert(xmldoc)
```

> [!NOTE]
> 若要了解有关 XML DOM 的详细信息和所有属性和方法，它支持，请参阅 MSDN 上的 MSXML SDK。 
  

