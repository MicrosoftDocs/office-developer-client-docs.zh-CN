---
title: 解决在设计时使用 InfoPath 对象模型的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003-compatible form templates, troubleshooting at design time,troubleshooting form templates [InfoPath 2007], design time
localization_priority: Normal
ms.assetid: 4179b235-e21d-4c37-ae2b-ad01388296ec
description: 以下各节介绍了在设计和调试使用由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的 InfoPath 2003 兼容对象模型的托管代码表单模板时，可能遇到的常见问题及解答。
ms.openlocfilehash: af71c8058744561a4c8ee0870fb37054e9979751
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774085"
---
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-design-time"></a><span data-ttu-id="95b45-104">解决在设计时使用 InfoPath 对象模型的表单模板</span><span class="sxs-lookup"><span data-stu-id="95b45-104">Troubleshoot form templates that use the InfoPath object model at design time</span></span>

<span data-ttu-id="95b45-105">以下各节介绍了在设计和调试使用由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 InfoPath 2003 兼容对象模型的托管代码表单模板时，可能遇到的常见问题及解答。</span><span class="sxs-lookup"><span data-stu-id="95b45-105">The following sections describe common troubleshooting scenarios you may encounter while designing and debugging managed code form templates that use the InfoPath 2003-compatible object model provided by the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace.</span></span> 
  
## <a name="cannot-preview-or-debug-form-templates-that-use-calls-to-object-model-security-level-3-methods-and-properties"></a><span data-ttu-id="95b45-106">无法预览和调试对对象模型安全级别 3 的方法和属性进行调用的表单模板</span><span class="sxs-lookup"><span data-stu-id="95b45-106">Cannot Preview or Debug Form Templates That Use Calls to Object Model Security Level 3 Methods and Properties</span></span>

<span data-ttu-id="95b45-107">如果您尝试调试或预览托管代码项目包含代码的调用对象模型成员需要完全信任，InfoPath 将显示错误消息"窗体的代码中发生了未处理的安全异常"并不能打开表单.</span><span class="sxs-lookup"><span data-stu-id="95b45-107">If you attempt to debug or preview a managed-code project that contains code that invokes object model members that require full trust, InfoPath will display the error message "An unhandled security exception has occurred in the form's code" and the form will not open.</span></span> <span data-ttu-id="95b45-108">要允许中要调试或预览的表单模板业务逻辑，必须将安全级别设置为**完全信任**并进行数字签名的表单模板。</span><span class="sxs-lookup"><span data-stu-id="95b45-108">To allow business logic in the form template to be debugged or previewed, you must set the security level to **Full Trust** and digitally sign the form template.</span></span> <span data-ttu-id="95b45-109">有关如何执行此操作的详细信息，请参阅[预览和调试表单模板的需要完全信任](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。</span><span class="sxs-lookup"><span data-stu-id="95b45-109">For details on how to do this, see [Preview and Debug Form Templates that Require Full Trust](how-to-preview-and-debug-form-templates-that-require-full-trust.md).</span></span>
  
## <a name="cannot-update-xpath-expressions-in-event-handlers-if-the-matchpath-parameter-value-was-deleted-manually"></a><span data-ttu-id="95b45-110">手动删除 MatchPath 参数值后无法更新事件处理程序中的 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="95b45-110">Cannot Update XPath Expressions in Event Handlers If the MatchPath Parameter Value Was Deleted Manually</span></span>

<span data-ttu-id="95b45-111">如果您将事件处理程序添加到域或组，并稍后更改影响的域或组 （例如，通过重命名或移动其） 一种方法中的 InfoPath**字段**任务窗格中的数据源的架构，将询问您是否要更新为显示一条消息e XPath 窗体的代码中的表达式。</span><span class="sxs-lookup"><span data-stu-id="95b45-111">If you add an event handler to a field or group and later change the schema of the data source in the InfoPath **Fields** task pane in a way that affects that field or group (for example, by renaming or moving it), a message will be displayed asking if you want to update the XPath expressions in your form's code.</span></span> <span data-ttu-id="95b45-112">此消息中引用的 XPath 表达式是[InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx)属性的[MatchPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx)参数中指定的值用于字段或窗体的数据源中的组相关联的事件处理程序.</span><span class="sxs-lookup"><span data-stu-id="95b45-112">The XPath expressions referred to in this message are the values specified in the [MatchPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx) parameter of the [InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx) attribute, which are used to associate the event handler with a field or group in your form's data source.</span></span> <span data-ttu-id="95b45-113">将不更新您的代码中的任何其他 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="95b45-113">No other XPath expressions in your code will be updated.</span></span> <span data-ttu-id="95b45-114">更新的 XPath 表达式的算法取决于未出席的**InfoPathEventHandler**属性的表单代码中应用的**MatchPath**参数值。</span><span class="sxs-lookup"><span data-stu-id="95b45-114">The algorithm for updating the XPath expressions depends on a value being present in the **MatchPath** parameter of the **InfoPathEventHandler** attributes that are applied in your form code.</span></span> <span data-ttu-id="95b45-115">如果手动删除这些值更新的 XPath 表达式的提示响应之前，InfoPath 将不能自动更新的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="95b45-115">If you manually deleted these values before responding to the prompt to update XPath expressions, InfoPath will not be able to update the XPath expressions automatically.</span></span> <span data-ttu-id="95b45-116">有关详细信息，请参阅[添加事件处理程序使用的 InfoPath 2003 对象模型](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="95b45-116">For more information, see [Add an Event Handler Using the InfoPath 2003 Object Model](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md).</span></span>
  
## <a name="cannot-call-members-of-the-infopath-2003-compatible-object-model-on-a-separate-thread"></a><span data-ttu-id="95b45-117">无法在单独的线程上调用 InfoPath 2003 兼容对象模型的成员</span><span class="sxs-lookup"><span data-stu-id="95b45-117">Cannot Call Members of the InfoPath 2003 Compatible Object Model on a Separate Thread</span></span>

<span data-ttu-id="95b45-p103">InfoPath 2003 兼容对象模型不支持在单独的线程上进行调用。例如，以下代码调用名为 LaunchOMFunction 的函数，该函数调用 InfoPath 对象模型的成员，因此代码将不会运行。</span><span class="sxs-lookup"><span data-stu-id="95b45-p103">The InfoPath 2003-compatible object model does not support calls on a separate thread. For example, the following code, which calls a function named LaunchOMFunction that calls members of the InfoPath object model, will not run.</span></span> 
  
```cs
Thread th = new Thread(new ThreadStart(LaunchOMFunction));
th.Start();
```

<span data-ttu-id="95b45-p104">必要时，可以通过某种方法来避开此限制。有关信息，请参阅[使用 InfoPath 2003 对象模型的 InfoPath 项目中的线程支持](threading-support-in-infopath-projects-using-the-infopath-2003-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="95b45-p104">When necessary, there is a way to work around this limitation. For information, see [Threading Support in InfoPath Projects Using the InfoPath 2003 Object Model](threading-support-in-infopath-projects-using-the-infopath-2003-object-model.md).</span></span>
  
## <a name="omitting-optional-parameters-causes-a-build-error-in-visual-basic-and-visual-c"></a><span data-ttu-id="95b45-122">省略可选参数导致 Visual Basic 和 Visual C# 中发生生成错误</span><span class="sxs-lookup"><span data-stu-id="95b45-122">Omitting Optional Parameters Causes a Build Error in Visual Basic and Visual C#</span></span>

<span data-ttu-id="95b45-p105">如果 InfoPath 对象模型成员包含一个可选参数，并且您没有为该参数指定值，则必须为该参数传递 **Type.Missing** 域。如果在忽略实际值时未能传递 **Type.Missing** 域，将导致生成错误。对于用 Visual Basic 编码的代码和用 Visual C# 编写的代码，都会存在这一问题。有关详细信息和示例，请参阅 [InfoPath 2003 兼容对象模型](infopath-2003-compatible-object-models.md)主题中的"向 InfoPath 对象模型成员传递可选参数"一节。</span><span class="sxs-lookup"><span data-stu-id="95b45-p105">If an InfoPath object model member contains an optional parameter, and you do not specify a value for that parameter, you must pass the **Type.Missing** field for that parameter instead. Failure to pass the **Type.Missing** field when an actual value is omitted will result in a build error. This is true for code written in both Visual Basic and Visual C#. For more information and examples see the "Passing Optional Parameters to InfoPath Object Model Members" section in the [InfoPath 2003 Compatible Object Models](infopath-2003-compatible-object-models.md) topic.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="95b45-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95b45-127">See also</span></span>

- [<span data-ttu-id="95b45-128">关于包含代码的表单模板的安全模型</span><span class="sxs-lookup"><span data-stu-id="95b45-128">About the Security Model for Form Templates with Code</span></span>](about-the-security-model-for-form-templates-with-code.md)
- [<span data-ttu-id="95b45-129">部署包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="95b45-129">Deploy InfoPath Form Templates with Code</span></span>](how-to-deploy-infopath-form-templates-with-code.md)
- [<span data-ttu-id="95b45-130">使用 InfoPath 2003 对象模型处理错误</span><span class="sxs-lookup"><span data-stu-id="95b45-130">Handle Errors Using the InfoPath 2003 Object Model</span></span>](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [<span data-ttu-id="95b45-131">预览和调试需要完全信任的表单模板</span><span class="sxs-lookup"><span data-stu-id="95b45-131">Preview and Debug Form Templates that Require Full Trust</span></span>](how-to-preview-and-debug-form-templates-that-require-full-trust.md)
- [<span data-ttu-id="95b45-132">使用 InfoPath 2003 对象模型调试 InfoPath 项目</span><span class="sxs-lookup"><span data-stu-id="95b45-132">Debug InfoPath Projects Using the InfoPath 2003 Object Model</span></span>](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)

