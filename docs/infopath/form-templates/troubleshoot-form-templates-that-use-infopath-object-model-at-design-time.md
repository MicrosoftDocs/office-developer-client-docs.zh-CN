---
title: 在设计时使用 InfoPath 对象模型的表单模板的疑难解答
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- infopath 2003 兼容的表单模板, 在设计时进行故障排除表单模板 [InfoPath 2007], 设计时
localization_priority: Normal
ms.assetid: 4179b235-e21d-4c37-ae2b-ad01388296ec
description: 以下各节介绍了在设计和调试使用由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的 InfoPath 2003 兼容对象模型的托管代码表单模板时，可能遇到的常见问题及解答。
ms.openlocfilehash: 106f12602bae86d85c2a7d2f920f59d50326c908
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303470"
---
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-design-time"></a>在设计时使用 InfoPath 对象模型的表单模板的疑难解答

以下各节介绍了在设计和调试使用由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 InfoPath 2003 兼容对象模型的托管代码表单模板时，可能遇到的常见问题及解答。 
  
## <a name="cannot-preview-or-debug-form-templates-that-use-calls-to-object-model-security-level-3-methods-and-properties"></a>无法预览和调试对对象模型安全级别 3 的方法和属性进行调用的表单模板

如果您尝试调试或预览的托管代码项目所包含的代码调用需要完全信任的对象模型成员，InfoPath 将显示错误消息“表单的代码中发生了未处理的安全异常”，并且不会打开表单。 要允许调试或预览表单模板中的业务逻辑，必须将安全级别设置为“完全信任”**** 并对表单模板进行数字签名。 有关如何执行此操作的详细信息, 请参阅[预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)。
  
## <a name="cannot-update-xpath-expressions-in-event-handlers-if-the-matchpath-parameter-value-was-deleted-manually"></a>手动删除 MatchPath 参数值后无法更新事件处理程序中的 XPath 表达式

如果在域或组中添加了事件处理程序，之后又在 InfoPath“域”**** 任务窗格中对数据源的架构进行了影响该域或组的更改（例如进行重命名或移动），系统将显示一条消息，询问您是否要更新表单代码中的 XPath 表达式。 此邮件中引用的 XPath 表达式是在[InfoPathEventHandlerAttribute](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.aspx)属性的[MatchPath](https://msdn.microsoft.com/library/Microsoft.Office.Interop.InfoPath.SemiTrust.InfoPathEventHandlerAttribute.MatchPath.aspx)参数中指定的值, 用于将事件处理程序与表单的数据源中的域或组相关联。. 代码中的其他任何 XPath 表达式都不会更新。 更新 XPath 表达式的算法取决于应用于表单代码中 **InfoPathEventHandler** 属性的 **MatchPath** 参数中的值。 如果您在响应 XPath 表达式更新提示之前手动删除了这些值，InfoPath 将无法自动更新 XPath 表达式。 有关详细信息, 请参阅[使用 InfoPath 2003 对象模型添加事件处理程序](how-to-add-an-event-handler-using-the-infopath-2003-object-model.md)。
  
## <a name="cannot-call-members-of-the-infopath-2003-compatible-object-model-on-a-separate-thread"></a>无法在单独的线程上调用 InfoPath 2003 兼容对象模型的成员

InfoPath 2003 兼容对象模型不支持在单独的线程上进行调用。 例如，以下代码调用名为 LaunchOMFunction 的函数，该函数调用 InfoPath 对象模型的成员，因此代码将不会运行。 
  
```cs
Thread th = new Thread(new ThreadStart(LaunchOMFunction));
th.Start();
```

必要时，可以通过某种方法来避开此限制。 有关信息, 请参阅[使用 infopath 2003 对象模型的 infopath 项目中的线程支持](threading-support-in-infopath-projects-using-the-infopath-2003-object-model.md)。
  
## <a name="omitting-optional-parameters-causes-a-build-error-in-visual-basic-and-visual-c"></a>省略可选参数导致 Visual Basic 和 Visual C# 中发生生成错误

如果 InfoPath 对象模型成员包含一个可选参数，并且您没有为该参数指定值，则必须为该参数传递 **Type.Missing** 域。 如果在忽略实际值时未能传递 **Type.Missing** 域，将会导致生成错误。 对于用 Visual Basic 编码的代码和用 Visual C# 编写的代码，都会存在这一问题。 有关详细信息和示例, 请参阅[InfoPath 2003 兼容对象模型](infopath-2003-compatible-object-models.md)主题中的 "将可选参数传递给 infopath 对象模型成员" 部分。 
  
## <a name="see-also"></a>另请参阅

- [关于包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
- [部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)
- [使用 InfoPath 2003 对象模型处理错误](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [预览和调试需要完全信任的表单模板](how-to-preview-and-debug-form-templates-that-require-full-trust.md)
- [使用 InfoPath 2003 对象模型调试 InfoPath 项目](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)

