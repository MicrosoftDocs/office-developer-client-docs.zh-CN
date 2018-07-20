---
title: 使用 InfoPath 2003 对象模型显示警报和对话框
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, displaying dialog boxes,form templates [InfoPath 2007], displaying dialog boxes,alerts, displaying in InfoPath 2003-compatible form templates,dialog boxes, displaying in InfoPath 2003-compatible form templates,InfoPath 2003-compatible form templates, displaying alerts
localization_priority: Normal
ms.assetid: 721ac58e-56d9-4e3b-93f1-849e0c94d010
description: 编写代码以扩展使用 InfoPath 2003 对象模型的表单模板的功能时，通过对话框向用户提供信息是非常有帮助的。
ms.openlocfilehash: 1cc0f4c7a6696eae2d3b7058898b4119cede79e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773990"
---
# <a name="display-alerts-and-dialog-boxes-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型显示警报和对话框

编写代码以扩展使用 InfoPath 2003 对象模型的表单模板的功能时，通过对话框向用户提供信息是非常有帮助的。在 InfoPath 中，以编程方式显示对话框和相关用户界面元素是通过使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口的方法来实现的。 
  
## <a name="overview-of-the-uiobject-interface"></a>UIObject 接口概述

[UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口提供下列方法，表单开发人员可以用来在 InfoPath 用户填写表单时向其显示不同类型的对话框。 
  
|名称|说明|
|:-----|:-----|
|[Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) <br/> |显示一个包含指定消息字符串的简单消息框。 无需用户输入任何内容而仅需显示消息时，应使用此方法。 通过单击“确定”**** 按钮将关闭显示的对话框。  <br/> |
|[Confirm](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Confirm.aspx) <br/> |显示一个带有用户输入按钮的消息框。返回值是 [XdConfirmChoice](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdConfirmChoice.aspx) 枚举常量之一。  <br/> |
|[SetSaveAsDialogFileName](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.SetSaveAsDialogFileName.aspx) <br/> |在“另存为”**** 对话框中设置表单的默认文件名。  <br/> |
|[SetSaveAsDialogLocation](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.SetSaveAsDialogLocation.aspx) <br/> |设置“另存为”**** 对话框在打开时开始浏览的初始位置。  <br/> |
|[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx) <br/> |在默认的电子邮件应用程序中新建电子邮件，当前打开的表单附加到该邮件中。  <br/> |
|[ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) <br/> |基于指定的 .html 文件和位置参数显示模式对话框。如果要向用户显示的不仅仅是一条简单的消息，并且您需要从用户处获得一些数据（除了由 **Confirm** 方法显示的"是" | “否”**** | ****“取消”按钮提供的简单确认****）。  <br/> |
|[ShowSignatureDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowSignatureDialog.aspx) <br/> |显示内置的“数字签名”**** 对话框。  <br/> |
   
## <a name="using-the-uiobject-interface"></a>使用 UIObject 接口

可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口（该接口本身可通过表单代码类的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.UI.aspx) 方法中初始化了的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 变量进行访问）的 `thisXDocument` 属性访问 `_Startup` 接口。以下示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx) 接口的 [ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 和 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法。 
  
```cs
thisXDocument.UI.ShowMailItem("someone@example.com","", "", 
   "Updated Form", "Here is the updated form that you requested.");
thisXDocument.UI.Alert("The email message has been created.");
```

```vb
thisXDocument.UI.ShowMailItem("someone@example.com", "", "", _
   "Updated Form", "Here is the updated form that you requested.")
thisXDocument.UI.Alert("The email message has been created.")
```

## <a name="using-the-showmodaldialog-method"></a>使用 ShowModalDialog 方法

该示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 接口的 [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法来显示在 HTML 文件 show.html 中定义的自定义对话框。 
  
```cs
public void CTRL1_5_OnClick(DocActionEvent e)
{
   // Write your code here.
   thisXDocument.UI.ShowModalDialog(
      "show.html",(object)thisXDocument,200,450,50,50);
}
```

```vb
Public Sub CTRL1_5_OnClick(ByVal e As DocActionEvent)
   ' Write your code here.
   thisXDocument.UI.ShowModalDialog( _
      "show.html", _
      DirectCast(thisXDocument, Object), 200, 450, 50, 50)
End Sub

```

Visual C# 和 Visual Basic 示例均依赖一个名为"show.html"的 HTML 文件，该文件定义由 [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 方法调用的对话框。该 HTML 文件显示表单中的一些数据，并显示一个文本框以便用户填入值。关闭对话框时，文本框中的值将返回到表单。 
  
```html
<HTML>
   <HEAD>
      <script language="JScript">
function BtnClick()
{
   xdocument = window.dialogArguments;
   myXml = xdocument.DOM.xml
   aForm = oForm.elements;
   aForm.textBox.value = myXml;
}
      </script>
   </HEAD>
   <BODY>
      <H1><FONT face="Arial">This is a modal dialog box</FONT> &nbsp;
      </H1>
      <BUTTON onclick="BtnClick()" id="BUTTON1" type="button">
         Get XML DOM
      </BUTTON>
      <FORM ID="oForm">
         <INPUT Type="text" name="textBox">
      </FORM>
   </BODY>
</HTML>

```

> [!IMPORTANT]
> [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 方法需要完全信任才能运行或预览。 有关详细信息，请参阅[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。 
  

