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
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-design-time"></a>解决在设计时使用 InfoPath 对象模型的表单模板

以下各节介绍了在设计和调试使用由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 InfoPath 2003 兼容对象模型的托管代码表单模板时，可能遇到的常见问题及解答。 
  
## <a name="cannot-preview-or-debug-form-templates-that-use-calls-to-object-model-security-level-3-methods-and-properties"></a>无法预览和调试对对象模型安全级别 3 的方法和属性进行调用的表单模板

如果您尝试调试或预览托管代码项目包含代码的调用对象模型成员需要完全信任，InfoPath 将显示错误消息"窗体的代码中发生了未处理的安全异常"并不能打开表单. 要允许中要调试或预览的表单模板业务逻辑，必须将安全级别设置为**完全信任**并进行数字签名的表单模板。 有关如何执行此操作的详细信息，请参阅[预览和调试表单模板的需要完全信任](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。
  
## <a name="cannot-update-xpath-expressions-in-event-handlers-if-the-matchpath-parameter-value-was-deleted-manually"></a>手动删除 MatchPath 参数值后无法更新事件处理程序中的 XPath 表达式

如果您将事件处理程序添加到域或组，并稍后更改影响的域或组 （例如，通过重命名或移动其） 一种方法中的 InfoPath**字段**任务窗格中的数据源的架构，将询问您是否要更新为显示一条消息e XPath 窗体的代码中的表达式。 此消息中引用的 XPath 表达式是[InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx)属性的[MatchPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx)参数中指定的值用于字段或窗体的数据源中的组相关联的事件处理程序. 将不更新您的代码中的任何其他 XPath 表达式。 更新的 XPath 表达式的算法取决于未出席的**InfoPathEventHandler**属性的表单代码中应用的**MatchPath**参数值。 如果手动删除这些值更新的 XPath 表达式的提示响应之前，InfoPath 将不能自动更新的 XPath 表达式。 有关详细信息，请参阅[添加事件处理程序使用的 InfoPath 2003 对象模型](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。
  
## <a name="cannot-call-members-of-the-infopath-2003-compatible-object-model-on-a-separate-thread"></a>无法在单独的线程上调用 InfoPath 2003 兼容对象模型的成员

InfoPath 2003 兼容对象模型不支持在单独的线程上进行调用。例如，以下代码调用名为 LaunchOMFunction 的函数，该函数调用 InfoPath 对象模型的成员，因此代码将不会运行。 
  
```cs
Thread th = new Thread(new ThreadStart(LaunchOMFunction));
th.Start();
```

必要时，可以通过某种方法来避开此限制。有关信息，请参阅[使用 InfoPath 2003 对象模型的 InfoPath 项目中的线程支持](threading-support-in-infopath-projects-using-the-infopath-2003-object-model.md)。
  
## <a name="omitting-optional-parameters-causes-a-build-error-in-visual-basic-and-visual-c"></a>省略可选参数导致 Visual Basic 和 Visual C# 中发生生成错误

如果 InfoPath 对象模型成员包含一个可选参数，并且您没有为该参数指定值，则必须为该参数传递 **Type.Missing** 域。如果在忽略实际值时未能传递 **Type.Missing** 域，将导致生成错误。对于用 Visual Basic 编码的代码和用 Visual C# 编写的代码，都会存在这一问题。有关详细信息和示例，请参阅 [InfoPath 2003 兼容对象模型](infopath-2003-compatible-object-models.md)主题中的"向 InfoPath 对象模型成员传递可选参数"一节。 
  
## <a name="see-also"></a>另请参阅

- [关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
- [部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)
- [使用 InfoPath 2003 对象模型处理错误](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)
- [调试使用 InfoPath 2003 对象模型的 InfoPath 项目](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)

