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
ms.openlocfilehash: 84c32244454e388e50433922c007d556fbef806a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774014"
---
# <a name="work-with-views"></a><span data-ttu-id="d9b84-105">使用视图</span><span class="sxs-lookup"><span data-stu-id="d9b84-105">Work with Views?</span></span>

<span data-ttu-id="d9b84-p102">使用 InfoPath 表单模板时，您可以编写代码来访问表单的视图，然后对视图包含的数据执行各种操作。[Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) 命名空间提供的 InfoPath 对象模型支持通过使用 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类的成员来访问表单的视图。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p102">When working with an InfoPath form template, you can write code to access the form's views, and then perform a variety of actions on the data that the views contain. The InfoPath object model provided by the [Microsoft.Office.InfoPath](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.aspx) namespace supports access to a form's views through the use of the members of the [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class.</span></span> 
  
## <a name="overview-of-the-view-class"></a><span data-ttu-id="d9b84-108">View 类概述</span><span class="sxs-lookup"><span data-stu-id="d9b84-108">Overview of the View Class</span></span>

<span data-ttu-id="d9b84-109">[View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类提供了下列方法和属性，供表单开发人员用来与 InfoPath 视图交互。</span><span class="sxs-lookup"><span data-stu-id="d9b84-109">The [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class provides the following methods and properties, which form developers can use to interact with an InfoPath view.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9b84-110">[View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类的方法和属性在 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件期间不可用。</span><span class="sxs-lookup"><span data-stu-id="d9b84-110">The methods and properties of the [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class are not available during the [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) event.</span></span> 
  
|<span data-ttu-id="d9b84-111">**名称**</span><span class="sxs-lookup"><span data-stu-id="d9b84-111">**Name**</span></span>|<span data-ttu-id="d9b84-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="d9b84-112">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9b84-113">[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.DisableAutoUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-113">[DisableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.DisableAutoUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-114">禁用表单的基础 XML 文档与相关视图之间的自动同步。</span><span class="sxs-lookup"><span data-stu-id="d9b84-114">Disables automatic synchronization between a form's underlying XML document and the associated view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-115">[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.EnableAutoUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-115">[EnableAutoUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.EnableAutoUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-116">启用表单的基础 XML 文档与相关视图之间的自动同步。</span><span class="sxs-lookup"><span data-stu-id="d9b84-116">Enables automatic synchronization between a form's underlying XML document and the associated view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-117">[ExecuteAction(ActionType)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-117">[ExecuteAction(ActionType)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-118">基于当前在视图中选择的数据，针对表单的基础 XML 文档执行编辑命令。</span><span class="sxs-lookup"><span data-stu-id="d9b84-118">Executes an editing command against a form's underlying XML document, based on the data currently selected in the view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-119">[ExecuteAction(ActionType, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-119">[ExecuteAction(ActionType, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ExecuteAction.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-120">基于指定的域和组，针对表单的基础 XML 文档执行编辑命令。</span><span class="sxs-lookup"><span data-stu-id="d9b84-120">Executes an editing command against a form's underlying XML document, based on the specified field or group.</span></span>  <br/> |
|<span data-ttu-id="d9b84-121">[Export](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Export.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-121">[Export](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Export.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-122">将视图导出为指定格式的文件。</span><span class="sxs-lookup"><span data-stu-id="d9b84-122">Exports the view to a file of the specified format.</span></span>  <br/> |
|<span data-ttu-id="d9b84-123">[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ForceUpdate.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-123">[ForceUpdate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ForceUpdate.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-124">在表单的基础 XML 文档与相关视图之间强制进行同步。</span><span class="sxs-lookup"><span data-stu-id="d9b84-124">Forces synchronization between a form's underlying XML document and the associated view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-125">[GetContextNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-125">[GetContextNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-126">获取一个对 **XPathNodeIterator** 对象的引用，以便从指定节点开始对返回的 XML 节点进行迭代。</span><span class="sxs-lookup"><span data-stu-id="d9b84-126">Gets a reference to an **XPathNodeIterator** object for iterating over the returned XML nodes starting from the specified node.</span></span>  <br/> |
|<span data-ttu-id="d9b84-127">[GetContextNodes(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-127">[GetContextNodes(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetContextNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-128">获取一个对 **XPathNodeIterator** 对象的引用，用于对绑定到指定域或组的控件内的当前所选项中的返回 XML 节点进行迭代。</span><span class="sxs-lookup"><span data-stu-id="d9b84-128">Gets a reference to an **XPathNodeIterator** object for iterating over the returned XML nodes in the current selection within the control bound to the specified field or group.</span></span>  <br/> |
|<span data-ttu-id="d9b84-129">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-129">[GetSelectedNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.GetSelectedNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-130">获取一个对 **XPathNodeIterator** 对象的引用，用于对视图内当前所选项中的所有 XML 节点进行迭代。</span><span class="sxs-lookup"><span data-stu-id="d9b84-130">Gets a reference to an **XPathNodeIterator** object for iterating over all XML nodes in the current selection of items in a view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-131">[SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-131">[SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-132">基于指定的起始 XML 节点在视图中选择一定范围的节点。</span><span class="sxs-lookup"><span data-stu-id="d9b84-132">Selects a range of nodes in a view based on the specified starting XML node.</span></span>  <br/> |
|<span data-ttu-id="d9b84-133">[SelectNodes(XPathNavigator, XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-133">[SelectNodes(XPathNavigator, XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-134">基于指定的起始 XML 节点和结束 XML 节点，在视图中选择一定范围的节点。</span><span class="sxs-lookup"><span data-stu-id="d9b84-134">Selects a range of nodes in a view based on the specified starting XML node and ending XML node.</span></span>  <br/> |
|<span data-ttu-id="d9b84-135">[SelectNodes(XPathNavigator, XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-135">[SelectNodes(XPathNavigator, XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-136">基于指定的开始 XML 节点、结束 XML 节点和指定控件，在视图中选择一定范围的节点。</span><span class="sxs-lookup"><span data-stu-id="d9b84-136">Selects a range of nodes in a view based on the specified starting XML node, the ending XML node, and the specified control.</span></span>  <br/> |
|<span data-ttu-id="d9b84-137">[SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-137">[SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-138">选择某个可编辑控件中包含的文本，该控件绑定到由传递到此方法的 **XPathNavigator** 对象所指定的节点。</span><span class="sxs-lookup"><span data-stu-id="d9b84-138">Selects the text contained in an editable control that is bound to the node specified by the **XPathNavigator** object passed to this method.</span></span>  <br/> |
|<span data-ttu-id="d9b84-139">[SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-139">[SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-140">选择某个可编辑控件（该控件绑定到由传递到此方法的 **XPathNavigator** 对象所指定的节点）和指定的控件中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="d9b84-140">Selects the text contained in an editable control that is bound to the node specified by the **XPathNavigator** object passed to this method, and the specified control.</span></span>  <br/> |
|<span data-ttu-id="d9b84-141">[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ShowMailItem.aspx) 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-141">[ShowMailItem](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ShowMailItem.aspx) method</span></span>  <br/> |<span data-ttu-id="d9b84-142">创建包含当前视图的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d9b84-142">Creates an e-mail message containing the current view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-143">[ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ViewInfo.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="d9b84-143">[ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.ViewInfo.aspx) property</span></span>  <br/> |<span data-ttu-id="d9b84-144">获取一个对与视图关联的 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="d9b84-144">Gets a reference to a [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) object associated with the view.</span></span>  <br/> |
|<span data-ttu-id="d9b84-145">[Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Window.aspx) 属性</span><span class="sxs-lookup"><span data-stu-id="d9b84-145">[Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.Window.aspx) property</span></span>  <br/> |<span data-ttu-id="d9b84-146">获取一个对与视图关联的 [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="d9b84-146">Gets a reference to a [Window](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Window.aspx) object associated with the view.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d9b84-147">InfoPath 对象模型还提供 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 和 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 类，这两个类可用于获取有关表单中实现的所有视图的信息。</span><span class="sxs-lookup"><span data-stu-id="d9b84-147">The InfoPath object model also provides the [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) and [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) classes, which can be used to get information about all of the views implemented in a form.</span></span> 
  
## <a name="using-the-view-class"></a><span data-ttu-id="d9b84-148">使用 View 类</span><span class="sxs-lookup"><span data-stu-id="d9b84-148">Using the View Class</span></span>

<span data-ttu-id="d9b84-p103">通过 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类（可使用 [this](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.CurrentView.aspx) (C#) 或 [Me](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) (Visual Basic) 关键字访问该类）的 **CurrentView** 属性可以访问 **View** 类。若要访问视图的名称，您需要访问与视图关联的 [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) 对象。例如，以下示例演示如何显示包含当前活动视图名称的消息框。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p103">The [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class is accessed through the [CurrentView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.CurrentView.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class, which is accessed using the **this** (C#) or **Me** (Visual Basic) keyword. To access the name of the view, you need to access the [ViewInfo](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfo.aspx) object associated with the view. The following example demonstrates how to display a message box with the name of the view that is currently active.</span></span> 
  
```cs
MessageBox.Show("Current view name: " + 
   this.CurrentView.ViewInfo.Name);
```

```vb
MessageBox.Show("Current view name: " &amp; _
   Me.CurrentView.ViewInfo.Name)
```

<span data-ttu-id="d9b84-p104">所有 InfoPath 表单模板都至少包含一个默认视图；但是，InfoPath 还支持为表单的基础 XML 文档创建多个视图。如果您有多个视图，则可以使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 来处理在表单模板中实现的所有视图。若要访问表单模板的 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) ，请使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.ViewInfos.aspx) 类的 [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性。可以使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.SwitchView.aspx) 的 [SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 方法通过编程方式更改当前活动的视图，如以下代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p104">All InfoPath form templates contain at least one default view; however, InfoPath also supports the creation of multiple views of a form's underlying XML document. When you have multiple views, the [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) can be used to work with all of the views implemented in the form template. To access the [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) of a form template, use the [ViewInfos](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.ViewInfos.aspx) property of the [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) class. You can programmatically change the view that is currently active by using the [SwitchView](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.SwitchView.aspx) method of the [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) , as the following code sample demonstrates.</span></span> 
  
```cs
this.ViewInfos.SwitchView("MySecondView");
```

```vb
Me.ViewInfos.SwitchView("MySecondView")
```

<span data-ttu-id="d9b84-p105">前面关于切换视图的示例仅在表单打开之后才有效。若要在 [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) 事件期间设置默认视图，请使用 [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.Initial.aspx) 类的 [Initial](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) 属性，如以下示例所示。但请注意，该值仅在表单保存后再次打开时才生效。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p105">The previous example for switching a view will work only after the form is opened. To set a default view during the [Loading](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.FormEvents.Loading.aspx) event, use the [Initial](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.Initial.aspx) property of the [ViewInfoCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.ViewInfoCollection.aspx) class as shown in the following example. Note, however, that this value will only take effect after the form is saved and re-opened.</span></span> 
  
```cs
this.ViewInfos.Initial = this.ViewInfos["MyInitialView"];
```

```vb
Me.ViewInfos.Initial = Me.ViewInfos["MyInitialView"];
```

## <a name="selecting-controls-in-a-view"></a><span data-ttu-id="d9b84-159">选择视图中的控件</span><span class="sxs-lookup"><span data-stu-id="d9b84-159">Selecting Controls in a View</span></span>

<span data-ttu-id="d9b84-160">InfoPath 提供了 [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) 类的下面两种方法（均为重载方法），用于以编程方式选择当前视图中的控件：[SelectText()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 和 [SelectNodes()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="d9b84-160">InfoPath provides two methods of the [View](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.aspx) class, both of which are overloaded, to programmatically select a control in the current view: the [SelectText()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) and [SelectNodes()](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) methods.</span></span> <span data-ttu-id="d9b84-161">[SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法用于数据输入控件（如**文本框**），而 **SelectNodes** 方法则用于结构控件（如**可选节**）。</span><span class="sxs-lookup"><span data-stu-id="d9b84-161">The [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) method is used for data entry controls, such as a **Text Box**, while the **SelectNodes** method is used for structural controls, such as an **Optional Section**.</span></span> <span data-ttu-id="d9b84-162">若要选择视图中的特定控件，需要提供节点，并视情况提供控件的 ViewContext ID。</span><span class="sxs-lookup"><span data-stu-id="d9b84-162">To select a particular control in the view, you need to provide the node and, optionally, the control's ViewContext ID.</span></span> <span data-ttu-id="d9b84-163">若有多个控件绑定到数据源中的相同节点，就需要提供 ViewContext ID。</span><span class="sxs-lookup"><span data-stu-id="d9b84-163">The ViewContext ID is needed when you have multiple controls bound to the same node in the data source.</span></span> <span data-ttu-id="d9b84-164">设计窗体时，InfoPath 用于提供 ViewContext ID 信息。</span><span class="sxs-lookup"><span data-stu-id="d9b84-164">InfoPath provides the ViewContext ID information when you design the form.</span></span>
  
<span data-ttu-id="d9b84-165">控件的 ViewContext ID 显示在控件属性对话框的“高级”**** 选项卡上，访问方法为右键单击控件，再依次单击“ControlName 属性”__**** 和“高级”**** 选项卡。“高级”**** 选项卡的“代码”**** 部分中列出了控件的 ViewContext ID。</span><span class="sxs-lookup"><span data-stu-id="d9b84-165">A control's ViewContext ID is displayed on the **Advanced** tab of the control's properties dialog box, which is accessed by right-clicking the control, clicking _ControlName _ **Properties**, and then clicking the **Advanced** tab. The ViewContext ID of the control is listed in the **Code** section of the **Advanced** tab.</span></span> 
  
## <a name="when-to-use-selecttext-and-selectnodes"></a><span data-ttu-id="d9b84-166">何时使用 SelectText 和 SelectNodes</span><span class="sxs-lookup"><span data-stu-id="d9b84-166">When to use SelectText and SelectNodes</span></span>

<span data-ttu-id="d9b84-167">您可以使用 [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 方法通过编程方式选择下列数据输入控件：</span><span class="sxs-lookup"><span data-stu-id="d9b84-167">You can programmatically select the following data entry controls by using the [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) method:</span></span> 
  
- <span data-ttu-id="d9b84-168">文本框</span><span class="sxs-lookup"><span data-stu-id="d9b84-168">Text Box</span></span>
    
- <span data-ttu-id="d9b84-169">格式文本框</span><span class="sxs-lookup"><span data-stu-id="d9b84-169">Rich Text Box</span></span>
    
- <span data-ttu-id="d9b84-170">日期选取器</span><span class="sxs-lookup"><span data-stu-id="d9b84-170">Date Picker</span></span>
    
<span data-ttu-id="d9b84-171">您可以使用 [SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法通过编程方式选择下列结构性控件：</span><span class="sxs-lookup"><span data-stu-id="d9b84-171">You can programmatically select the following structural controls by using the [SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) method:</span></span> 
  
- <span data-ttu-id="d9b84-172">可选节</span><span class="sxs-lookup"><span data-stu-id="d9b84-172">Optional Section</span></span>
    
- <span data-ttu-id="d9b84-173">选项节</span><span class="sxs-lookup"><span data-stu-id="d9b84-173">Choice Section</span></span>
    
- <span data-ttu-id="d9b84-174">重复节（项）</span><span class="sxs-lookup"><span data-stu-id="d9b84-174">Repeating Section (items)</span></span>
    
- <span data-ttu-id="d9b84-175">重复表（行）</span><span class="sxs-lookup"><span data-stu-id="d9b84-175">Repeating Table (rows)</span></span>
    
- <span data-ttu-id="d9b84-176">重复递归节（项）</span><span class="sxs-lookup"><span data-stu-id="d9b84-176">Repeating Recursive Section (items)</span></span>
    
- <span data-ttu-id="d9b84-177">项目符号列表、编号列表和普通列表</span><span class="sxs-lookup"><span data-stu-id="d9b84-177">Bulleted, Numbered, and Plain List</span></span>
    
- <span data-ttu-id="d9b84-178">水平重复表</span><span class="sxs-lookup"><span data-stu-id="d9b84-178">Horizontal Repeating Table</span></span>
    
<span data-ttu-id="d9b84-179">不能以编程方式选择以下控件或将焦点设置到以下控件：</span><span class="sxs-lookup"><span data-stu-id="d9b84-179">You cannot programmatically select, or set focus to, the following controls:</span></span>
  
- <span data-ttu-id="d9b84-180">下拉列表框</span><span class="sxs-lookup"><span data-stu-id="d9b84-180">Drop-Down List Box</span></span>
    
- <span data-ttu-id="d9b84-181">列表框</span><span class="sxs-lookup"><span data-stu-id="d9b84-181">List Box</span></span>
    
- <span data-ttu-id="d9b84-182">复选框</span><span class="sxs-lookup"><span data-stu-id="d9b84-182">Check Box</span></span>
    
- <span data-ttu-id="d9b84-183">选项按钮</span><span class="sxs-lookup"><span data-stu-id="d9b84-183">Option Button</span></span>
    
- <span data-ttu-id="d9b84-184">按钮</span><span class="sxs-lookup"><span data-stu-id="d9b84-184">Button</span></span>
    
- <span data-ttu-id="d9b84-185">图片（链接的或包含的）</span><span class="sxs-lookup"><span data-stu-id="d9b84-185">Picture (linked or included)</span></span>
    
- <span data-ttu-id="d9b84-186">墨迹图片</span><span class="sxs-lookup"><span data-stu-id="d9b84-186">Ink Picture</span></span>
    
- <span data-ttu-id="d9b84-187">超链接</span><span class="sxs-lookup"><span data-stu-id="d9b84-187">Hyperlink</span></span>
    
- <span data-ttu-id="d9b84-188">表达式框</span><span class="sxs-lookup"><span data-stu-id="d9b84-188">Expression Box</span></span>
    
- <span data-ttu-id="d9b84-189">竖排标签</span><span class="sxs-lookup"><span data-stu-id="d9b84-189">Vertical Label</span></span>
    
- <span data-ttu-id="d9b84-190">ActiveX 节</span><span class="sxs-lookup"><span data-stu-id="d9b84-190">ActiveX Section</span></span>
    
- <span data-ttu-id="d9b84-191">水平区域</span><span class="sxs-lookup"><span data-stu-id="d9b84-191">Horizontal Region</span></span>
    
## <a name="using-the-selecttext-and-selectnodes-methods"></a><span data-ttu-id="d9b84-192">使用 SelectText 和 SelectNodes 方法</span><span class="sxs-lookup"><span data-stu-id="d9b84-192">Using the SelectText and SelectNodes Methods</span></span>

<span data-ttu-id="d9b84-193">在下面的示例中，**SelectText** 方法的 [SelectText(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 重载（提供一个 _xmlNode_ 参数）用于选择绑定到“my:field1”的**文本框**。</span><span class="sxs-lookup"><span data-stu-id="d9b84-193">In the following example, the [M:Microsoft.Office.InfoPath.View.SelectText(System.Xml.XPath.XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) overload of the **SelectText** method, which provides one _xmlNode_ parameter, is used to select a **Text Box** that is bound to "my:field1".</span></span> 
  
```cs
// Create XPathNavigator and select field.
XPathNavigator textNode = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:field1", NamespaceManager);
// Select text in specified field.
CurrentView.SelectText(textNode);
```

<span data-ttu-id="d9b84-194">若有多个控件绑定到“my:field1”，必须使用 **SelectText** 方法的 [SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) 重载，其中额外提供了可用于选择特定控件的 _viewContext_ 参数。</span><span class="sxs-lookup"><span data-stu-id="d9b84-194">If you have multiple controls bound to "my:field1", you must use the [SelectText(XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectText.aspx) overload of the **SelectText** method, which provides an additional  _viewContext_ parameter to select a specific control.</span></span> <span data-ttu-id="d9b84-195">下面的示例假定有两个**文本框**控件绑定到“my:field1”，第一个控件的 ViewContext ID 为“CTRL1”，第二个控件的 ViewContext ID 为“CTRL8”。</span><span class="sxs-lookup"><span data-stu-id="d9b84-195">If you have multiple controls bound to "my:field1", you must use the M:Microsoft.Office.InfoPath.View.SelectText(System.Xml.XPath.XPathNavigator,System.String) overload of the SelectText method, which provides an additional viewContext parameter to select a specific control. The following example assumes that there are two **Text Box** controls bound to "my:field1", with the first control having a ViewContext ID of "CTRL1" and the second control having a ViewContext ID of "CTRL8". The second control is selected.</span></span> <span data-ttu-id="d9b84-196">选择的是第二个控件。</span><span class="sxs-lookup"><span data-stu-id="d9b84-196">The second control is selected.</span></span> 
  
```cs
// Create XPathNavigator and select field.
XPathNavigator textNode = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:field1", NamespaceManager);
// Select text in specified field.
CurrentView.SelectText(textNode, "CTRL8");
```

<span data-ttu-id="d9b84-197">在以下示例中，可以使用 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法的 **SelectNodes(XPathNavigator)** 重载（只提供一个  _startNode_ 参数）来选择绑定到重复组"my:employee"的重复表的第一行。</span><span class="sxs-lookup"><span data-stu-id="d9b84-197">In the following example, the [SelectNodes(XPathNavigator)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) overload of the **SelectNodes** method, which provides only one  _startNode_ parameter, is used to select the first row in a repeating table bound to the repeating group "my:employee".</span></span> 
  
```cs
// Create XPathNavigator and specify XPath for nodes.
XPathNavigator repeatingTableRow1 = 
   CreateNavigator().SelectSingleNode(
   "/my:myFields/my:employees/my:employee[1]", NamespaceManager);
// Select nodes in specified XPathNavigator.
CurrentView.SelectNodes(repeatingTableRow1);
```

<span data-ttu-id="d9b84-p108">也可以选择重复表中的多行。在以下示例中，可以使用 [SelectNodes](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) 方法的 **SelectNodes(XPathNavigator, XPathNavigator, String)** 重载（提供  _startNode_ 和  _endNode_ 参数）来选择绑定到重复组"my:employee"的重复表的前三行：</span><span class="sxs-lookup"><span data-stu-id="d9b84-p108">You can also select multiple rows in a repeating table. In the following example, the first three rows of a repeating table bound to the repeating group "my:employee" are selected using the [SelectNodes(XPathNavigator, XPathNavigator, String)](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.View.SelectNodes.aspx) overload of the **SelectNodes** method, which provides  _startNode_ and  _endNode_ parameters:</span></span> 
  
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


