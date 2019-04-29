---
title: 处理错误
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- errors [infopath 2007], handling,FormErrorCollection [InfoPath 2007],InfoPath 2007, error handling,FormError [InfoPath 2007],error handling [InfoPath 2007]
localization_priority: Normal
ms.assetid: 132cb698-d9a5-4767-b3d1-5dd1343a1ff4
description: 创建自定义应用程序时，开发人员必须经常执行错误处理，这包括通过编写程序代码，检查是否存在应用程序引起的错误，或者创建和引发自定义错误。Microsoft.Office.InfoPath 命名空间提供的 InfoPath 对象模型支持通过使用与 FormErrorCollection 类关联的 FormError 类来处理错误。
ms.openlocfilehash: 30cf649188b7e4cbc35469d2a50540bb13ecb38d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410775"
---
# <a name="handle-errors"></a>处理错误

创建自定义应用程序时，开发人员必须经常执行错误处理，这包括通过编写程序代码，检查是否存在应用程序引起的错误，或者创建和引发自定义错误。[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 对象模型支持通过使用与 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) 类关联的 [FormError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 类来处理错误。 
  
在 InfoPath 中，发生错误的原因包括：
  
- 输入到表单的数据未通过 XML 架构的验证。
    
- 自定义验证约束失败。
    
- 错误由 [XmlValidatingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) 事件对象的 [ReportError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.aspx) 方法生成。 
    
- 使用 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 类的 [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 方法时引发了用户定义的错误。 
    
## <a name="overview-of-the-formerrorcollection-class"></a>FormErrorCollection 类概述

[FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 类提供了下列方法和属性，表单开发人员可使用这些属性和方法来管理该集合包含的 [FormError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) 对象。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 方法（+3 个重载）  <br/> |创建一个 **FormError** 对象，并将其添加到集合中。  <br/> |
|[Delete](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Delete.aspx) 方法（+1 个重载）  <br/> |从集合中删除指定的用户定义错误。  <br/> |
|[DeleteAll](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.DeleteAll.aspx) 方法  <br/> |删除包含在集合中的所有 **FormError** 对象。  <br/> |
|[GetErrors](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.GetErrors.aspx) （+1 个重载）  <br/> |从集合中返回指定名称或类型的所有 **FormError** 对象。  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Count.aspx) 属性  <br/> |获取集合中包含的 **FormError** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Item.aspx) 属性  <br/> |基于指定的索引编号获取对 **FormError** 对象的引用。  <br/> |
   
## <a name="overview-of-the-formerror-class"></a>FormError 类概述

[FormError](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.aspx) 类提供了以下属性，表单开发人员可以使用这些属性来访问有关所引发的错误的信息。 
  
|**名称**|**说明**|
|:-----|:-----|
|[DetailedMessage](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.DetailedMessage.aspx) 属性  <br/> |获取或设置 **FormError** 对象的详细错误消息。  <br/> |
|[ErrorCode](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.ErrorCode.aspx) 属性  <br/> |获取或设置 **FormError** 对象的错误代码。  <br/> |
|[Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.Site.aspx) 属性  <br/> |获取位于与 **FormError** 对象关联的节点中的 **XPathNavigator** 对象。  <br/> |
|[Message](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.Message.aspx) 属性  <br/> |获取或设置 **FormError** 对象的短错误消息。  <br/> |
|[FormErrorType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormError.FormErrorType.aspx) 属性  <br/> |获取 **FormError** 对象的类型。  <br/> |
   
## <a name="using-the-formerrorcollection-and-formerror-classes"></a>使用 FormErrorCollection 和 FormError 类

通过使用 **XmlForm** 对象的 [Errors](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Errors.aspx) 属性可以访问与表单关联的 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 对象。 **FormErrorCollection** 对象与表单的基础 XML 文件相关联，这样，当发生错误时，可以在当前 XML 文档内访问和管理该错误及其他所有错误。下面的示例演示如何使用循环来检查表单的基础 XML 文档中可能存在的错误。如果存在错误，函数将循环遍历每个错误，并使用 **FormError** 对象的 **Message** 属性向用户显示一个消息框。 
  
```cs
public void CheckErrors(XPathNavigator xmlNode)
{
   foreach(FormError err in this.Errors)
   {
      if(xmlNode.InnerXml == err.Site.InnerXml)
         MessageBox.Show("The following error has occured: "
             + err.Message);
   }
}
```

```vb
Public Sub CheckErrors(ByVal xmlNode As XPathNavigator)
   Dim err As FormError
   For Each err In Me.Errors
      If xmlNode.InnerXml = err.Site.InnerXml Then
         MessageBox.Show("The following error has occured: " _
             &amp; err.Message)
   End If
End Sub
```

可以通过表单的数据验证事件处理程序之一来调用前面的函数。例如，当在表单中某个域的 [Changed](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEvent.Changed.aspx) 事件的事件处理程序中使用时，对该函数的调用将使用 [XmlEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.Site.aspx) 事件对象的 [Site](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlEventArgs.aspx) 属性来传递 XML 节点参数，如下所示： 
  
```cs
CheckErrors(e.Site);
```

```vb
CheckErrors(e.Site)
```

除了处理由 InfoPath 生成的错误以外，表单开发人员还可以通过使用 [ReportError(XPathNavigator, Boolean, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) 事件对象的 [XmlValidatingEventArgs](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.aspx) 方法，或者通过使用 [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 类的 [FormErrorCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.aspx) 方法来生成自定义错误。有关使用 [ReportError(XPathNavigator, Boolean, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlValidatingEventArgs.ReportError.aspx) 或 [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormErrorCollection.Add.aspx) 方法的信息，请单击本主题开头这些方法的链接。 
  
## <a name="handling-managed-code-exceptions"></a>处理托管代码异常

可以使用 try-catch 异常处理方法来处理在托管代码表单模板中引发的异常，如以下代码示例所示。
  
```cs
FileQueryConnection queryXMLFile = 
   (FileQueryConnection)this.DataConnections["form1"];
// Perform the query.
try
{
   queryXMLFile.Execute();
}
catch (Exception ex)
{
   MessageBox.Show("Failed to query." + System.Environment.NewLine 
      + ex.Message);
}
```

```vb
Dim queryXMLFile As FileQueryConnection = _
   DirectCast(Me.DataConnections("form1"), FileQueryConnection)
' Perform the query.
Try
   queryXMLFile.Execute();
Catch ex As Exception
   MessageBox.Show("Failed to query." &amp; System.Environment.NewLine 
      &amp; ex.Message)
End Try
```

如果在表单代码中不使用 try-catch 异常处理方法，则在调试和预览过程中，InfoPath 将在 InfoPath 错误对话框中显示有关未处理的异常的信息。此外，默认情况下，当您部署托管代码表单模板时，未处理的异常不会在运行时显示在 InfoPath 错误对话框中。要在运行时显示有关未处理的异常的信息，请执行以下过程。
  
### <a name="enable-notifications-for-unhandled-managed-code-exceptions-at-run-time"></a>在运行时针对未处理的托管代码异常启用通知

1. 打开 InfoPath Designer，然后单击“文件”**** 选项卡。 
    
2. 单击“选项”****，然后单击“常规”**** 类别下的“InfoPath 选项”****。 
    
3. 在“高级”**** 选项卡上，选中****“显示 Visual Basic 和 C# 代码错误的通知”复选框。 
    

