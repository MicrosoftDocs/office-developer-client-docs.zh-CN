---
title: 使用 InfoPath 2003 对象模型处理错误
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, handling errors,InfoPath 2003-compatible form templates, error handling,form templates [InfoPath 2007], error handling,error handling [InfoPath 2007], InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: eeb05205-d6f4-4931-b9a9-55a663bb1a25
description: 创建自定义应用程序时，开发人员必须经常执行错误处理，这包括通过编写程序代码，检查是否存在应用程序引起的错误，或者创建和引发自定义错误。InfoPath 2003 兼容对象模型通过使用与 ErrorsCollection 集合关联的 ErrorObject 对象，来支持错误处理。
ms.openlocfilehash: 577e531d8943dc8fc3884cd81f68b11ca285c5d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774005"
---
# <a name="handle-errors-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型处理错误

创建自定义应用程序时，开发人员必须经常执行错误处理，这包括通过编写程序代码，检查是否存在应用程序引起的错误，或者创建和引发自定义错误。InfoPath 2003 兼容对象模型通过使用与 [ErrorsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ErrorObject.aspx) 集合关联的 [ErrorObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ErrorsCollection.aspx) 对象，来支持错误处理。 
  
在 InfoPath 中，在以下情况中会发生错误：输入到表单中的数据未能通过 XML 架构验证，自定义的有效性约束失败，[DataDOMEventObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.ReportError.aspx) 对象的 [ReportError](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEventObject.aspx) 方法产生错误，或者使用 [ErrorsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.Add.aspx) 集合的 [Add](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ErrorsCollection.aspx) 方法引发错误。 
  
## <a name="overview-of-the-errorscollection-collection"></a>ErrorsCollection 集合概述

**ErrorsCollection** 集合提供了下列方法和属性，表单开发人员可以将其用于管理该集合包含的 **ErrorObject** 对象。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Add](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.Add.aspx) 方法  <br/> |创建 **ErrorObject** 对象并将其添加到集合中。  <br/> |
|[Delete](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.Delete.aspx) 方法  <br/> |删除与指定的 XML 节点和条件名称相关联的所有 **ErrorObject** 对象，但使用 **ReportError** 方法添加的自定义错误除外。  <br/> |
|[DeleteAll](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.DeleteAll.aspx) 方法  <br/> |删除包含在集合中的所有 **ErrorObject** 对象。  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.Count.aspx) 属性  <br/> |获取集合所包含的 **ErrorObject** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Errors.Item.aspx) 属性  <br/> |基于指定索引号获取对 **ErrorObject** 对象的引用。  <br/> |
   
## <a name="overview-of-the-errorobject-object"></a>ErrorObject 对象概述

**ErrorObject** 对象提供了如下属性，表单开发人员可以用它们来访问关于所引发的错误的信息。 
  
|**名称**|**说明**|
|:-----|:-----|
|[ConditionName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.ConditionName.aspx) 属性  <br/> |根据 **ErrorObject** 对象的类型，获取错误条件的名称或者返回 **null**。  <br/> |
|[DetailedErrorMessage](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.DetailedErrorMessage.aspx) 属性  <br/> |获取或设置 **ErrorObject** 对象的详细错误消息。  <br/> |
|[ErrorCode](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.ErrorCode.aspx) 属性  <br/> |获取或设置 **ErrorObject** 对象的错误代码。  <br/> |
|[Node](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.Node.aspx) 属性  <br/> |获取对与 **ErrorObject** 对象关联的 XML 节点的引用。  <br/> |
|[ShortErrorMessage](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.ShortErrorMessage.aspx) 属性  <br/> |获取或设置 **ErrorObject** 对象的短错误消息。  <br/> |
|[ErrorType](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.Error.ErrorType.aspx) 属性  <br/> |获取 **ErrorObject** 对象的类型。  <br/> |
   
## <a name="using-the-errorscollection-and-errorobject"></a>使用 ErrorsCollection 和 ErrorObject

通过 **XDocument** 对象的 [Errors](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument.Errors.aspx) 属性可以访问 [ErrorsCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 集合。 **ErrorsCollection** 集合与表单的基础 XML 文档相关联，以便在发生错误时，该错误发生在 XML 文档内部。下例演示如何使用 Visual C# **foreach** 循环来检查在表单的基础 XML 文档中可能存在的错误。如果有错误，函数将循环遍历每个错误，并使用 **ErrorObject** 对象的 **ShortErrorMessage** 属性向用户显示消息框。 
  
```cs
public void CheckErrors(IXMLDOMNode xmlNode)
{
   foreach(ErrorObject err in thisXDocument.Errors)
   {
      if(xmlNode==err.Node)
         thisXDocument.UI.Alert("The following error has occured: "
             + err.ShortErrorMessage + ".");
   }
}
```

可以通过表单的数据验证事件处理程序之一来调用前面的函数。例如，在 [OnAfterChange](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._DataDOMEventSink_Event.OnAfterChange.aspx) 事件处理程序中用来处理表单中的域时，对该函数的调用将使用 [DataDOMEventObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEvent.Site.aspx) 对象的 [Site](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.DataDOMEventObject.aspx) 属性来传递 XML 节点参数，如下所示： 
  
```cs
CheckErrors(e.Site);
```

除了处理由 InfoPath 生成的错误以外，表单开发人员还可以使用 **DataDOMEventObject** 对象的 **ReportError** 方法，或者使用 **ErrorsCollection** 集合的 **Add** 方法，来生成自定义错误。有关使用 **ReportError** 或 **Add** 方法的信息，请单击本主题开头的方法。 
  
## <a name="handling-managed-code-exceptions"></a>处理托管代码异常

可以使用 try-catch 异常处理方法来处理在托管代码表单模板中引发的异常，如以下代码示例所示。
  
```cs
DataAdapters dataAdapters;
dataAdapters = thisXDocument.DataAdapters; 
XMLFileAdapterObject queryXMLFile = 
   (XMLFileAdapterObject)dataAdapters["form1"];
// Perform the query.
try
{
   queryXMLFile.Query();
}
catch (Exception ex)
{
   thisXDocument.UI.Alert("Failed to query.\n\n" + ex.Message);
}
// Perform the submit.
try
{
   queryXMLFile.Submit();
}
catch (Exception ex)
{
   thisXDocument.UI.Alert("Failed to submit.\n\n" + ex.Message);
}
```

如果表单代码中没有使用 try-catch 异常处理方法，则在调试和预览过程中，InfoPath 将在 InfoPath 错误对话框中显示有关未处理的异常的信息。 
  

