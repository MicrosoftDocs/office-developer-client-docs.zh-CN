---
title: 编写确定运行时环境的条件逻辑
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 在 infopath [infopath 2007] 中运行，运行时环境 [InfoPath 2007]，在浏览器 [InfoPath 2007] 中运行，InfoPath 2007，确定运行时环境
localization_priority: Normal
ms.assetid: 1a43bbdc-666b-47ef-a5e3-cb477a4deb04
description: Application 类的 Environment 属性获取对 Environment 对象的引用，该对象可用于确定表单是使用哪个运行时环境（InfoPath、Web 浏览器或移动浏览器）打开的。
ms.openlocfilehash: 31bfd8dcd05d52d6c6e162d4aa4838e423d97e0b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408598"
---
# <a name="write-conditional-logic-that-determines-the-run-time-environment"></a><span data-ttu-id="a7da7-104">编写确定运行时环境的条件逻辑</span><span class="sxs-lookup"><span data-stu-id="a7da7-104">Write Conditional Logic That Determines the Run-time Environment</span></span>

<span data-ttu-id="a7da7-105">[Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Environment.aspx) 类的 [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性获取对 [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) 对象的引用，该对象可用于确定表单是使用哪个运行时环境（InfoPath、Web 浏览器或移动浏览器）打开的。</span><span class="sxs-lookup"><span data-stu-id="a7da7-105">The [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Environment.aspx) property of the [Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) class gets a reference to an [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) object, which can be used to determine which runtime environment (InfoPath, Web browser, or mobile browser) was used to open the form.</span></span> 
  
## <a name="example"></a><span data-ttu-id="a7da7-106">示例</span><span class="sxs-lookup"><span data-stu-id="a7da7-106">Example</span></span>

### <a name="determining-which-runtime-environment-a-form-is-running-in"></a><span data-ttu-id="a7da7-107">确定运行表单的运行时环境</span><span class="sxs-lookup"><span data-stu-id="a7da7-107">Determining Which Runtime Environment a Form is Running In</span></span>

<span data-ttu-id="a7da7-p101">[Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) 类提供 [IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) 和 [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) 属性，这两个属性可用来判断表单模板是在哪种编辑环境下打开的。如果两个属性都返回 **false**，则表单模板是在 Microsoft InfoPath 编辑器中打开的。如果任意一个属性返回 **true**，则表单模板是在运行 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上针对相应属性进行适当配置的文档库打开的：[IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) 属性对应 Web 浏览器， [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) 属性对应移动浏览器。</span><span class="sxs-lookup"><span data-stu-id="a7da7-p101">The [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) class provides the [IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) and [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) properties that enable you to determine what editing environment was used to open a form template. If both properties return **false**, the form template was opened in the Microsoft InfoPath editor. If either property returns **true**, the form template was opened from an appropriately configured document library on Microsoft SharePoint Server 2010 running InfoPath Forms Services in the program for the corresponding property: a Web browser ([IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) property) or a mobile browser ( [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) property).</span></span> 
  
<span data-ttu-id="a7da7-p102">In the following example, if the form is opened in a browser or mobile browser, the value of field1 (which is bound to a **Text Box** control) is set to a string to indicate which runtime environment the form was opened in. If the form is opened in InfoPath, the **System.Windows.Forms.MessageBox.Show** method (which isn't available when a form is running in a browser) is used to display a message box.</span><span class="sxs-lookup"><span data-stu-id="a7da7-p102">In the following example, if the form is opened in a browser or mobile browser, the value of field1 (which is bound to a **Text Box** control) is set to a string to indicate which runtime environment the form was opened in. If the form is opened in InfoPath, the **System.Windows.Forms.MessageBox.Show** method (which isn't available when a form is running in a browser) is used to display a message box.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a7da7-p103">When you create the form template for the following code sample, select the **Blank** template on the **New** tab of the Backstage view. (Alternatively, you can select **Web Browser Form** from the **Form type** drop-down list under the **Compatibility** category of the **Form Options** dialog box.) To support the **MessageBox** class, add a reference to **System.Windows.Forms** on the . **NET** tab of the **Add Reference** dialog box in Visual Studio 2012, and then add a **using** or **Imports** directive for **System.Windows.Forms** in the declarations section of the form code module.</span><span class="sxs-lookup"><span data-stu-id="a7da7-p103">When you create the form template for the following code sample, select the **Blank** template on the **New** tab of the Backstage view. (Alternatively, you can select **Web Browser Form** from the **Form type** drop-down list under the **Compatibility** category of the **Form Options** dialog box.) To support the **MessageBox** class, add a reference to **System.Windows.Forms** on the . **NET** tab of the **Add Reference** dialog box in Visual Studio 2012, and then add a **using** or **Imports** directive for **System.Windows.Forms** in the declarations section of the form code module.</span></span> 
  
```cs
if(this.Application.Environment.IsBrowser)
{
   CreateNavigator().SelectSingleNode(
      "/my:myFields/my:field1", NamespaceManager).
      SetValue("Running in a browser.");
}
else if (this.Application.Environment.IsMobile)
{
   CreateNavigator().SelectSingleNode(
      "/my:myFields/my:field1", NamespaceManager).
      SetValue("Running in a mobile browser.");
}
else
{
   MessageBox.Show("This form is running in the InfoPath editor.");
}
```

```vb
If (Me.Application.Environment.IsBrowser) Then
   CreateNavigator().SelectSingleNode(_
      "/my:myFields/my:field1", NamespaceManager). _
      SetValue("Running in a browser.")
ElseIf (Me.Application.Environment.IsMobile) Then
   CreateNavigator().SelectSingleNode( _
      "/my:myFields/my:field1", NamespaceManager). _
      SetValue("Running in a mobile browser.")
Else
   MessageBox.Show("This form is running in the InfoPath editor.")
End If
```


