---
title: 使用 InfoPath 2003 对象模型处理视图
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, views,views [InfoPath 2007], InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: feb1bfcb-1cb1-4d5c-bc84-df86a33a5934
description: 使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。InfoPath 2003 兼容对象模型支持通过使用 ViewObject 接口的成员来访问表单的视图。
ms.openlocfilehash: 6a2dd408ba51e5c8394120944e0c28897e768738
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299875"
---
# <a name="work-with-views-using-the-infopath-2003-object-model"></a>使用 InfoPath 2003 对象模型处理视图

使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。InfoPath 2003 兼容对象模型支持通过使用 [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口的成员来访问表单的视图。 
  
## <a name="overview-of-the-viewobject-interface"></a>ViewObject 接口概述

[ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口提供了下列方法和属性，表单开发人员可以使用这些方法和属性与 InfoPath 视图进行交互。 
  
> [!NOTE]
> [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口的方法和属性在 [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 事件过程中不可用。 
  
|**名称**|**说明**|
|:-----|:-----|
|[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.DisableAutoUpdate.aspx) 方法  <br/> |禁用 XML 文档对象模型 (DOM) 与视图的同步。  <br/> |
|[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.EnableAutoUpdate.aspx) 方法  <br/> |启用 XML DOM 与视图的同步。  <br/> |
|[ExecuteAction](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ExecuteAction.aspx) 方法  <br/> |执行 InfoPath 编辑操作。  <br/> |
|[Export](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Export.aspx) 方法  <br/> |将视图导出为指定格式的文件。  <br/> |
|[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ForceUpdate.aspx) 方法  <br/> |使 XML DOM 与视图保持同步。  <br/> |
|[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetContextNodes.aspx) 方法  <br/> |基于指定的 XML 节点和视图上下文，或者基于视图中的当前所选项，返回对 [XMLNodesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLNodesCollection.aspx) 接口的引用。  <br/> |
|[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetSelectedNodes.aspx) 方法  <br/> |基于视图中的当前所选项，返回对 **XMLNodesCollection** 接口的引用。  <br/> |
|[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectNodes.aspx) 方法  <br/> |在视图中选择一定范围的 XML 节点。  <br/> |
|[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectText.aspx) 方法  <br/> |选择包含在视图中指定 XML 节点内的文本。  <br/> |
|[SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SwitchView.aspx) 方法  <br/> |将 InfoPath 表单切换到指定的视图  <br/> |
|[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Name.aspx) 属性  <br/> |返回表示当前视图名称的字符串值。  <br/> |
|[Window](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Window.aspx) 属性  <br/> |返回对 [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowObject.aspx) 接口的引用，该接口访问与视图关联的 **Window**。  <br/> |
   
> [!NOTE]
> InfoPath 2003 兼容对象模型还提供 [ViewInfosCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfosCollection.aspx) 接口，该接口可用于获得在表单中实现的所有视图的相关信息。 
  
## <a name="using-the-viewobject-interface"></a>使用 ViewObject 接口

可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口（该接口可通过在表单代码类的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.View.aspx) 方法中初始化的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 变量来访问）的 `thisXDocument` 属性访问 `_Startup` 接口。例如，下面的代码示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 接口的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法，通过消息框显示与表单的基础 XML 文档关联的当前视图的名称。 
  
```cs
thisXDocument.UI.Alert("Current view name: " + 
   thisXDocument.View.Name);
```

```vb
thisXDocument.UI.Alert("Current view name: " &amp; _
   thisXDocument.View.Name)
```

所有 InfoPath 表单都包含至少一个默认视图；但是，InfoPath 还支持为表单的基础 XML 文档创建多个视图。如果表单中有多个视图，则可以用 **View** 对象来处理当前处于活动状态的视图。可以用编程方式利用 **View** 对象的 **SwitchView** 方法来更改当前活动的视图，如下列代码示例所示。 
  
```cs
thisXDocument.View.SwitchView("MySecondView");
```

```vb
thisXDocument.View.SwitchView("MySecondView")
```

前面关于切换视图的示例仅在表单打开之后才有效。要设置 **OnLoad** 事件过程中的默认视图，请使用 [ViewInfoObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.IsDefault.aspx) 接口的 [IsDefault](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfoObject.aspx) 属性，如下面的示例所示。 
  
```cs
thisXDocument.ViewInfos["MyDefaultView"].IsDefault = true;
```

```vb
thisXDocument.ViewInfos("MyDefaultView").IsDefault = True
```


