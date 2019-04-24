---
title: 使用视图
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- view class [infopath 2007],InfoPath 2007, working with views,views [InfoPath 2007]
localization_priority: Normal
ms.assetid: 947b33c3-2acc-45d2-a89d-a712b6bc53df
description: 使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。Microsoft.Office.InfoPath 命名空间提供的 InfoPath 对象模型支持通过使用 View 类的成员来访问表单的视图。
ms.openlocfilehash: 829375a87513634ef0b38b6d92de9f33a605e89f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303540"
---
# <a name="work-with-views"></a>使用视图

使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 对象模型支持通过使用 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类的成员来访问表单的视图。 
  
## <a name="overview-of-the-view-class"></a>View 类概述

[View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类提供了下列方法和属性，供表单开发人员用来与 InfoPath 视图交互。 
  
> [!NOTE]
> [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类的方法和属性在 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件期间不可用。 
  
|**名称**|**说明**|
|:-----|:-----|
|[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.DisableAutoUpdate.aspx) 方法  <br/> |禁用表单的基础 XML 文档与相关视图之间的自动同步。  <br/> |
|[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.EnableAutoUpdate.aspx) 方法  <br/> |启用表单的基础 XML 文档与相关视图之间的自动同步。  <br/> |
|[ExecuteAction(ActionType)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) 方法  <br/> |基于当前在视图中选择的数据，针对表单的基础 XML 文档执行编辑命令。  <br/> |
|[ExecuteAction(ActionType, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) 方法  <br/> |基于指定的域和组，针对表单的基础 XML 文档执行编辑命令。  <br/> |
|[Export](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Export.aspx) 方法  <br/> |将视图导出为指定格式的文件。  <br/> |
|[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ForceUpdate.aspx) 方法  <br/> |在表单的基础 XML 文档与相关视图之间强制进行同步。  <br/> |
|[GetContextNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法  <br/> |获取一个对 **XPathNodeIterator** 对象的引用，以便从指定节点开始对返回的 XML 节点进行迭代。  <br/> |
|[GetContextNodes(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法  <br/> |获取一个对 **XPathNodeIterator** 对象的引用，用于对绑定到指定域或组的控件内的当前所选项中的返回 XML 节点进行迭代。  <br/> |
|[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) 方法  <br/> |获取一个对 **XPathNodeIterator** 对象的引用，用于对视图内当前所选项中的所有 XML 节点进行迭代。  <br/> |
|[SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法  <br/> |基于指定的起始 XML 节点在视图中选择一定范围的节点。  <br/> |
|[SelectNodes(XPathNavigator, XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法  <br/> |基于指定的起始 XML 节点和结束 XML 节点，在视图中选择一定范围的节点。  <br/> |
|[SelectNodes(XPathNavigator, XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法  <br/> |基于指定的开始 XML 节点、结束 XML 节点和指定控件，在视图中选择一定范围的节点。  <br/> |
|[SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法  <br/> |选择某个可编辑控件中包含的文本，该控件绑定到由传递到此方法的 **XPathNavigator** 对象所指定的节点。  <br/> |
|[SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法  <br/> |选择某个可编辑控件（该控件绑定到由传递到此方法的 **XPathNavigator** 对象所指定的节点）和指定的控件中包含的文本。  <br/> |
|[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ShowMailItem.aspx) 方法  <br/> |创建包含当前视图的电子邮件。  <br/> |
|[ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ViewInfo.aspx) 属性  <br/> |获取一个对与视图关联的 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 对象的引用。  <br/> |
|[Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Window.aspx) 属性  <br/> |获取一个对与视图关联的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象的引用。  <br/> |
   
> [!NOTE]
> InfoPath 对象模型还提供 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 和 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 类，这两个类可用于获取有关表单中实现的所有视图的信息。 
  
## <a name="using-the-view-class"></a>使用 View 类

通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类（可使用 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.CurrentView.aspx) (C#) 或 [Me](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) (Visual Basic) 关键字访问该类）的 **CurrentView** 属性可以访问 **View** 类。若要访问视图的名称，您需要访问与视图关联的 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 对象。例如，以下示例演示如何显示包含当前活动视图名称的消息框。 
  
```cs
MessageBox.Show("Current view name: " + 
   this.CurrentView.ViewInfo.Name);
```

```vb
MessageBox.Show("Current view name: " &amp; _
   Me.CurrentView.ViewInfo.Name)
```

所有 InfoPath 表单模板都至少包含一个默认视图；但是，InfoPath 还支持为表单的基础 XML 文档创建多个视图。如果您有多个视图，则可以使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 来处理在表单模板中实现的所有视图。若要访问表单模板的 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) ，请使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.ViewInfos.aspx) 类的 [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性。可以使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.SwitchView.aspx) 的 [SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 方法通过编程方式更改当前活动的视图，如以下代码示例所示。 
  
```cs
this.ViewInfos.SwitchView("MySecondView");
```

```vb
Me.ViewInfos.SwitchView("MySecondView")
```

前面关于切换视图的示例仅在表单打开之后才有效。若要在 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件期间设置默认视图，请使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.Initial.aspx) 类的 [Initial](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 属性，如以下示例所示。但请注意，该值仅在表单保存后再次打开时才生效。 
  
```cs
this.ViewInfos.Initial = this.ViewInfos["MyInitialView"];
```

```vb
Me.ViewInfos.Initial = Me.ViewInfos["MyInitialView"];
```

## <a name="selecting-controls-in-a-view"></a>选择视图中的控件

InfoPath provides two methods of the [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class, both of which are overloaded, to programmatically select a control in the current view: the [SelectText()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) and [SelectNodes()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) methods. The [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) method is used for data entry controls, such as a **Text Box**, while the **SelectNodes** method is used for structural controls, such as an **Optional Section**. To select a particular control in the view, you need to provide the node and, optionally, the control's ViewContext ID. The ViewContext ID is needed when you have multiple controls bound to the same node in the data source. InfoPath provides the ViewContext ID information when you design the form.
  
控件的 ViewContext ID 显示在控件属性对话框的“高级”**** 选项卡上，访问方法为右键单击控件，再依次单击“ControlName 属性”__**** 和“高级”**** 选项卡。“高级”**** 选项卡的“代码”**** 部分中列出了控件的 ViewContext ID。 
  
## <a name="when-to-use-selecttext-and-selectnodes"></a>何时使用 SelectText 和 SelectNodes

您可以使用 [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法通过编程方式选择下列数据输入控件： 
  
- 文本框
    
- 格式文本框
    
- 日期选取器
    
您可以使用 [SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法通过编程方式选择下列结构性控件： 
  
- 可选节
    
- 选项节
    
- 重复节（项）
    
- 重复表（行）
    
- 重复递归节（项）
    
- 项目符号列表、编号列表和普通列表
    
- 水平重复表
    
不能以编程方式选择以下控件或将焦点设置到以下控件：
  
- 下拉列表框
    
- 列表框
    
- 复选框
    
- 选项按钮
    
- 按钮
    
- 图片（链接的或包含的）
    
- 墨迹图片
    
- 超链接
    
- 表达式框
    
- 竖排标签
    
- ActiveX 节
    
- 水平区域
    
## <a name="using-the-selecttext-and-selectnodes-methods"></a>使用 SelectText 和 SelectNodes 方法

在下面的示例中，**SelectText** 方法的 [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 重载（提供一个 _xmlNode_ 参数）用于选择绑定到“my:field1”的**文本框**。 
  
```cs
// Create XPathNavigator and select field.
XPathNavigator textNode = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:field1", NamespaceManager);
// Select text in specified field.
CurrentView.SelectText(textNode);
```

If you have multiple controls bound to "my:field1", you must use the [SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) overload of the **SelectText** method, which provides an additional  _viewContext_ parameter to select a specific control. The following example assumes that there are two **Text Box** controls bound to "my:field1", with the first control having a ViewContext ID of "CTRL1" and the second control having a ViewContext ID of "CTRL8". The second control is selected. 
  
```cs
// Create XPathNavigator and select field.
XPathNavigator textNode = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:field1", NamespaceManager);
// Select text in specified field.
CurrentView.SelectText(textNode, "CTRL8");
```

在以下示例中，可以使用 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法的 **SelectNodes(XPathNavigator)** 重载（只提供一个  _startNode_ 参数）来选择绑定到重复组"my:employee"的重复表的第一行。 
  
```cs
// Create XPathNavigator and specify XPath for nodes.
XPathNavigator repeatingTableRow1 = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:employees/my:employee[1]", NamespaceManager);
// Select nodes in specified XPathNavigator.
CurrentView.SelectNodes(repeatingTableRow1);
```

也可以选择重复表中的多行。在以下示例中，可以使用 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法的 **SelectNodes(XPathNavigator, XPathNavigator, String)** 重载（提供  _startNode_ 和  _endNode_ 参数）来选择绑定到重复组"my:employee"的重复表的前三行： 
  
```cs
// Create XPathNavigators to specify range of nodes.
XPathNavigator repeatingTableRow1 = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:employees/my:employee[1]", NamespaceManager);
XPathNavigator repeatingTableRow3 = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:employees/my:myemployee[3]", NamespaceManager);
// Select range of nodes in specified XPathNavigators.
CurrentView.SelectNodes(repeatingTableRow1, repeatingTableRow3);
```


