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
# <a name="display-alerts-and-dialog-boxes-using-the-infopath-2003-object-model"></a><span data-ttu-id="f39aa-104">使用 InfoPath 2003 对象模型显示警报和对话框</span><span class="sxs-lookup"><span data-stu-id="f39aa-104">How to: Display Alerts and Dialog Boxes Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="f39aa-p101">编写代码以扩展使用 InfoPath 2003 对象模型的表单模板的功能时，通过对话框向用户提供信息是非常有帮助的。在 InfoPath 中，以编程方式显示对话框和相关用户界面元素是通过使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口的方法来实现的。</span><span class="sxs-lookup"><span data-stu-id="f39aa-p101">When writing code to extend the functionality of a form template that uses the InfoPath 2003 object model, it is often useful to provide the user with information in a dialog box. Programmatically displaying a dialog box and related user interface elements is accomplished in InfoPath by using the methods of the [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface.</span></span> 
  
## <a name="overview-of-the-uiobject-interface"></a><span data-ttu-id="f39aa-107">UIObject 接口概述</span><span class="sxs-lookup"><span data-stu-id="f39aa-107">Overview of the UIObject Interface</span></span>

<span data-ttu-id="f39aa-108">[UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口提供下列方法，表单开发人员可以用来在 InfoPath 用户填写表单时向其显示不同类型的对话框。</span><span class="sxs-lookup"><span data-stu-id="f39aa-108">The [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface provides the following methods, which form developers can use to have different types of dialog boxes displayed to InfoPath users as they are filling out a form.</span></span> 
  
|<span data-ttu-id="f39aa-109">名称</span><span class="sxs-lookup"><span data-stu-id="f39aa-109">Name</span></span>|<span data-ttu-id="f39aa-110">说明</span><span class="sxs-lookup"><span data-stu-id="f39aa-110">Description</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f39aa-111">Alert</span><span class="sxs-lookup"><span data-stu-id="f39aa-111">Alert</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) <br/> |<span data-ttu-id="f39aa-112">显示一个包含指定消息字符串的简单消息框。</span><span class="sxs-lookup"><span data-stu-id="f39aa-112">Displays a simple message box that contains a specified message string.</span></span> <span data-ttu-id="f39aa-113">无需用户输入任何内容而仅需显示消息时，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="f39aa-113">Displays a simple message box that contains a specified message string. This method should be used when no input is required from the user and only a message needs to be displayed. The dialog box displayed is closed by clicking the OK button.</span></span> <span data-ttu-id="f39aa-114">通过单击“确定”**** 按钮将关闭显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="f39aa-114">The dialog box displayed is closed by clicking the **OK** button.</span></span>  <br/> |
|[<span data-ttu-id="f39aa-115">Confirm</span><span class="sxs-lookup"><span data-stu-id="f39aa-115">Confirm</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Confirm.aspx) <br/> |<span data-ttu-id="f39aa-p103">显示一个带有用户输入按钮的消息框。返回值是 [XdConfirmChoice](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdConfirmChoice.aspx) 枚举常量之一。  </span><span class="sxs-lookup"><span data-stu-id="f39aa-p103">Displays a message box with buttons for input from a user. The value that is returned is one of the [XdConfirmChoice](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XdConfirmChoice.aspx) enumerated constants.  </span></span><br/> |
|[<span data-ttu-id="f39aa-118">SetSaveAsDialogFileName</span><span class="sxs-lookup"><span data-stu-id="f39aa-118">SetSaveAsDialogFileName</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.SetSaveAsDialogFileName.aspx) <br/> |<span data-ttu-id="f39aa-119">在“另存为”**** 对话框中设置表单的默认文件名。</span><span class="sxs-lookup"><span data-stu-id="f39aa-119">Sets the default file name for a form in the **Save As** dialog box.</span></span>  <br/> |
|<span data-ttu-id="f39aa-120">[SetSaveAsDialogLocation](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.SetSaveAsDialogLocation.aspx)</span><span class="sxs-lookup"><span data-stu-id="f39aa-120">[SetSaveAsDialogLocation](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.SetSaveAsDialogLocation.aspx) method</span></span> <br/> |<span data-ttu-id="f39aa-121">设置“另存为”**** 对话框在打开时开始浏览的初始位置。</span><span class="sxs-lookup"><span data-stu-id="f39aa-121">Sets the initial location at which the **Save As** dialog box starts to browse when it is opened.</span></span>  <br/> |
|<span data-ttu-id="f39aa-122">[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx)</span><span class="sxs-lookup"><span data-stu-id="f39aa-122">[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx) method</span></span> <br/> |<span data-ttu-id="f39aa-123">在默认的电子邮件应用程序中新建电子邮件，当前打开的表单附加到该邮件中。</span><span class="sxs-lookup"><span data-stu-id="f39aa-123">Creates a new e-mail message in the default e-mail application, with the currently open form attached to the message.</span></span>  <br/> |
|[<span data-ttu-id="f39aa-124">ShowModalDialog</span><span class="sxs-lookup"><span data-stu-id="f39aa-124">ShowModalDialog</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) <br/> |<span data-ttu-id="f39aa-p104">基于指定的 .html 文件和位置参数显示模式对话框。如果要向用户显示的不仅仅是一条简单的消息，并且您需要从用户处获得一些数据（除了由 **Confirm** 方法显示的"是"</span><span class="sxs-lookup"><span data-stu-id="f39aa-p104">Displays a modal dialog box, based on the specified .html file and positional arguments. This method should be used if you want to display more than a simple message to the user and you need to get back some data from the user (beyond the simple confirmation that is provided by the **Yes**</span></span> | <span data-ttu-id="f39aa-127">“否”****</span><span class="sxs-lookup"><span data-stu-id="f39aa-127">**No**</span></span> | <span data-ttu-id="f39aa-128">****“取消”按钮提供的简单确认****）。</span><span class="sxs-lookup"><span data-stu-id="f39aa-128">**Cancel** buttons displayed by the **Confirm** method).</span></span>  <br/> |
|[<span data-ttu-id="f39aa-129">ShowSignatureDialog</span><span class="sxs-lookup"><span data-stu-id="f39aa-129">ShowSignatureDialog</span></span>](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowSignatureDialog.aspx) <br/> |<span data-ttu-id="f39aa-130">显示内置的“数字签名”**** 对话框。</span><span class="sxs-lookup"><span data-stu-id="f39aa-130">Displays the built-in **Digital Signatures** dialog box.</span></span>  <br/> |
   
## <a name="using-the-uiobject-interface"></a><span data-ttu-id="f39aa-131">使用 UIObject 接口</span><span class="sxs-lookup"><span data-stu-id="f39aa-131">Using the UIObject Interface</span></span>

<span data-ttu-id="f39aa-p105">可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 接口（该接口本身可通过表单代码类的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.UI.aspx) 方法中初始化了的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 变量进行访问）的 `thisXDocument` 属性访问 `_Startup` 接口。以下示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx) 接口的 [ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 和 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="f39aa-p105">The [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface is accessed through the [UI](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.UI.aspx) property of the [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) interface, which itself is accessed through the  `thisXDocument` variable that is initialized in the  `_Startup` method of the form code class. The following example demonstrates using the [ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowMailItem.aspx) and [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) methods of the [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface.</span></span> 
  
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

## <a name="using-the-showmodaldialog-method"></a><span data-ttu-id="f39aa-134">使用 ShowModalDialog 方法</span><span class="sxs-lookup"><span data-stu-id="f39aa-134">Using the ShowModalDialog Method</span></span>

<span data-ttu-id="f39aa-135">该示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 接口的 [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法来显示在 HTML 文件 show.html 中定义的自定义对话框。</span><span class="sxs-lookup"><span data-stu-id="f39aa-135">This example demonstrates how to use the [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) method of the [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface to display a custom dialog box defined in the HTML file show.html.</span></span> 
  
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

<span data-ttu-id="f39aa-p106">Visual C# 和 Visual Basic 示例均依赖一个名为"show.html"的 HTML 文件，该文件定义由 [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 方法调用的对话框。该 HTML 文件显示表单中的一些数据，并显示一个文本框以便用户填入值。关闭对话框时，文本框中的值将返回到表单。</span><span class="sxs-lookup"><span data-stu-id="f39aa-p106">Both the Visual C# and Visual Basic samples depend on an HTML file named "show.html" that defines the dialog box that is invoked by the [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) method. This HTML file displays some data from the form and shows a text box for the user to fill in a value. The value in the textbox is returned to the form when the dialog box is closed.</span></span> 
  
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
> <span data-ttu-id="f39aa-139">[ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) 方法需要完全信任才能运行或预览。</span><span class="sxs-lookup"><span data-stu-id="f39aa-139">The [ShowModalDialog](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.ShowModalDialog.aspx) method requires Full Trust to run or preview.</span></span> <span data-ttu-id="f39aa-140">有关详细信息，请参阅[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。</span><span class="sxs-lookup"><span data-stu-id="f39aa-140">For more information, see [How to: Preview and Debug Form Templates that Require Full Trust](how-to-preview-and-debug-form-templates-that-require-full-trust.md).</span></span> 
  

