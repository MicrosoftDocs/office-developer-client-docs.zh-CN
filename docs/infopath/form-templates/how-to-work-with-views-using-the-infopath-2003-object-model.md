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
# <a name="work-with-views-using-the-infopath-2003-object-model"></a><span data-ttu-id="c68e7-105">使用 InfoPath 2003 对象模型处理视图</span><span class="sxs-lookup"><span data-stu-id="c68e7-105">Work with Views Using the InfoPath 2003 Object Model</span></span>

<span data-ttu-id="c68e7-p102">使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。InfoPath 2003 兼容对象模型支持通过使用 [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口的成员来访问表单的视图。</span><span class="sxs-lookup"><span data-stu-id="c68e7-p102">When working with an InfoPath form template, you can write code to access the form's views, and then perform a variety of actions on the data that the views contain. The InfoPath 2003-compatible object model supports access to a form's views through the use of the members of the [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) interface.</span></span> 
  
## <a name="overview-of-the-viewobject-interface"></a><span data-ttu-id="c68e7-108">ViewObject 接口概述</span><span class="sxs-lookup"><span data-stu-id="c68e7-108">Overview of the ViewObject Interface</span></span>

<span data-ttu-id="c68e7-109">[ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口提供了下列方法和属性，表单开发人员可以使用这些方法和属性与 InfoPath 视图进行交互。</span><span class="sxs-lookup"><span data-stu-id="c68e7-109">The [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) interface provides the following methods and properties, which form developers can use to interact with an InfoPath view.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c68e7-110">[ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口的方法和属性在 [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) 事件过程中不可用。</span><span class="sxs-lookup"><span data-stu-id="c68e7-110">The methods and properties of the [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) interface are not available during the [OnLoad](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocumentEventSink2_Event.OnLoad.aspx) event.</span></span> 
  
|<span data-ttu-id="c68e7-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="c68e7-111">**Name**</span></span>|<span data-ttu-id="c68e7-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="c68e7-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c68e7-113">[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.DisableAutoUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-113">[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.DisableAutoUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-114">禁用 XML 文档对象模型 (DOM) 与视图的同步。</span><span class="sxs-lookup"><span data-stu-id="c68e7-114">Disables synchronization of the XML Document Object Model (DOM) and the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-115">[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.EnableAutoUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-115">[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.EnableAutoUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-116">启用 XML DOM 与视图的同步。</span><span class="sxs-lookup"><span data-stu-id="c68e7-116">Enables synchronization of the XML DOM and the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-117">[ExecuteAction](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ExecuteAction.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-117">[ExecuteAction](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ExecuteAction.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-118">执行 InfoPath 编辑操作。</span><span class="sxs-lookup"><span data-stu-id="c68e7-118">Executes an InfoPath editing action.</span></span>  <br/> |
|<span data-ttu-id="c68e7-119">[Export](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Export.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-119">[Export](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Export.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-120">将视图导出为指定格式的文件。</span><span class="sxs-lookup"><span data-stu-id="c68e7-120">Exports the view as a file of the specified format.</span></span>  <br/> |
|<span data-ttu-id="c68e7-121">[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ForceUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-121">[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.ForceUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-122">使 XML DOM 与视图保持同步。</span><span class="sxs-lookup"><span data-stu-id="c68e7-122">Synchronizes the XML DOM and the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-123">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetContextNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-123">[GetContextNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetContextNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-124">基于指定的 XML 节点和视图上下文，或者基于视图中的当前所选项，返回对 [XMLNodesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLNodesCollection.aspx) 接口的引用。</span><span class="sxs-lookup"><span data-stu-id="c68e7-124">Returns a reference to the [XMLNodesCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XMLNodesCollection.aspx) interface, based on the specified XML node and view context or on the current selection in the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-125">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetSelectedNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-125">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.GetSelectedNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-126">基于视图中的当前所选项，返回对 **XMLNodesCollection** 接口的引用。</span><span class="sxs-lookup"><span data-stu-id="c68e7-126">Returns a reference to the **XMLNodesCollection** interface, based on the current selection in the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-127">[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-127">[SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-128">在视图中选择一定范围的 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="c68e7-128">Selects a range of XML nodes in the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-129">[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectText.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-129">[SelectText](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SelectText.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-130">选择包含在视图中指定 XML 节点内的文本。</span><span class="sxs-lookup"><span data-stu-id="c68e7-130">Selects the text contained in the specified XML node in the view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-131">[SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SwitchView.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="c68e7-131">[SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.SwitchView.aspx) method</span></span>  <br/> |<span data-ttu-id="c68e7-132">将 InfoPath 表单切换到指定的视图</span><span class="sxs-lookup"><span data-stu-id="c68e7-132">Switches an InfoPath form to the specified view</span></span>  <br/> |
|<span data-ttu-id="c68e7-133">[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Name.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="c68e7-133">[Name](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Name.aspx) property</span></span>  <br/> |<span data-ttu-id="c68e7-134">返回表示当前视图名称的字符串值。</span><span class="sxs-lookup"><span data-stu-id="c68e7-134">Returns a string value indicating the name of the current view.</span></span>  <br/> |
|<span data-ttu-id="c68e7-135">[Window](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Window.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="c68e7-135">[Window](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.View.Window.aspx) property</span></span>  <br/> |<span data-ttu-id="c68e7-136">返回对 [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowObject.aspx) 接口的引用，该接口访问与视图关联的 **Window**。</span><span class="sxs-lookup"><span data-stu-id="c68e7-136">Returns a reference to the [WindowObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.WindowObject.aspx) interface which accesses the **Window** associated with the view.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c68e7-137">InfoPath 2003 兼容对象模型还提供 [ViewInfosCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfosCollection.aspx) 接口，该接口可用于获得在表单中实现的所有视图的相关信息。</span><span class="sxs-lookup"><span data-stu-id="c68e7-137">The InfoPath 2003-compatible object model also provides the [ViewInfosCollection](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfosCollection.aspx) interface, which can be used to get information about all of the views implemented in a form.</span></span> 
  
## <a name="using-the-viewobject-interface"></a><span data-ttu-id="c68e7-138">使用 ViewObject 接口</span><span class="sxs-lookup"><span data-stu-id="c68e7-138">Using the ViewObject Interface</span></span>

<span data-ttu-id="c68e7-p103">可通过 [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) 接口（该接口可通过在表单代码类的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.View.aspx) 方法中初始化的  [](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) 变量来访问）的 `thisXDocument` 属性访问 `_Startup` 接口。例如，下面的代码示例演示如何使用 [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) 接口的 [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) 方法，通过消息框显示与表单的基础 XML 文档关联的当前视图的名称。</span><span class="sxs-lookup"><span data-stu-id="c68e7-p103">The [ViewObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewObject.aspx) interface is accessed through the [View](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust._XDocument2.View.aspx) property of the [XDocument](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.XDocument.aspx) interface (which is accessed through the  `thisXDocument` variable that is initialized in the  `_Startup` method of the form code class). For example, the following code sample demonstrates how to use the [Alert](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UI2.Alert.aspx) method of the [UIObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.UIObject.aspx) interface to display a message box with the name of the current view that is associated with a form's underlying XML document.</span></span> 
  
```cs
thisXDocument.UI.Alert("Current view name: " + 
   thisXDocument.View.Name);
```

```vb
thisXDocument.UI.Alert("Current view name: " &amp; _
   thisXDocument.View.Name)
```

<span data-ttu-id="c68e7-p104">所有 InfoPath 表单都包含至少一个默认视图；但是，InfoPath 还支持为表单的基础 XML 文档创建多个视图。如果表单中有多个视图，则可以用 **View** 对象来处理当前处于活动状态的视图。可以用编程方式利用 **View** 对象的 **SwitchView** 方法来更改当前活动的视图，如下列代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="c68e7-p104">All InfoPath forms contain at least one default view; however, InfoPath also supports the creation of multiple views of a form's underlying XML document. When you have multiple views in a form, the **View** object can be used to work with the view that is currently active. You can programmatically change the view that is currently active by using the **SwitchView** method of the **View** object, as the following code sample demonstrates.</span></span> 
  
```cs
thisXDocument.View.SwitchView("MySecondView");
```

```vb
thisXDocument.View.SwitchView("MySecondView")
```

<span data-ttu-id="c68e7-p105">前面关于切换视图的示例仅在表单打开之后才有效。要设置 **OnLoad** 事件过程中的默认视图，请使用 [ViewInfoObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.IsDefault.aspx) 接口的 [IsDefault](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfoObject.aspx) 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="c68e7-p105">The previous example for switching a view will work only after the form is opened. To set a default view during the **OnLoad** event, use the [IsDefault](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfo.IsDefault.aspx) property of the [ViewInfoObject](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.ViewInfoObject.aspx) interface, as shown in the following example.</span></span> 
  
```cs
thisXDocument.ViewInfos["MyDefaultView"].IsDefault = true;
```

```vb
thisXDocument.ViewInfos("MyDefaultView").IsDefault = True
```


