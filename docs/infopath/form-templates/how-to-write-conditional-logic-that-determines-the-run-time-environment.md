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
ms.openlocfilehash: b854d6a3b65fcc37375480bef9f1909d84407b6c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773988"
---
# <a name="write-conditional-logic-that-determines-the-run-time-environment"></a>编写确定运行时环境的条件逻辑

[Application](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.Environment.aspx) 类的 [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Application.aspx) 属性获取对 [Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) 对象的引用，该对象可用于确定表单是使用哪个运行时环境（InfoPath、Web 浏览器或移动浏览器）打开的。 
  
## <a name="example"></a>示例

### <a name="determining-which-runtime-environment-a-form-is-running-in"></a>确定运行表单的运行时环境

[Environment](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.aspx) 类提供 [IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) 和 [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) 属性，这两个属性可用来判断表单模板是在哪种编辑环境下打开的。如果两个属性都返回 **false**，则表单模板是在 Microsoft InfoPath 编辑器中打开的。如果任意一个属性返回 **true**，则表单模板是在运行 InfoPath Forms Services 的 Microsoft SharePoint Server 2010 上针对相应属性进行适当配置的文档库打开的：[IsBrowser](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsBrowser.aspx) 属性对应 Web 浏览器， [IsMobile](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Environment.IsMobile.aspx) 属性对应移动浏览器。 
  
在以下示例中，如果表单是在浏览器或移动浏览器中打开的，字段 1 （该字段绑定一个**文本框**控件）的值设定为一个字符串，用以指示打开表单的运行时环境。 如果表单是在 InfoPath 中打开的，则采用**System.Windows.Forms.MessageBox.Show**方法（如果表单是在浏览器中运行，则该方法不可用） 显示消息框。 
  
> [!IMPORTANT]
> 为以下代码示例创建表单模板时，请在 Backstage 视图的**新建**选项卡选择**空白**模板。 （或者，可以从**表单选项**对话框的**兼容性**类别下的**表单类型**下拉列表中选择** Web 浏览器表单**。）为支持 **MessageBox** 类，在 Visual Studio 2012 **添加引用**对话框的 . **NET** 选项卡上添加对System.Windows.Forms的引用，然后在表单代码模块的声明部分为**System.Windows.Forms**添加一个**使用**或**导入**指令。 
  
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


