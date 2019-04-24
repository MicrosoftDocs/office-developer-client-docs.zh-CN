---
title: 在运行时使用 InfoPath 对象模型的表单模板的疑难解答
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 表单模板疑难解答 [infopath 2007], 运行时, infopath 2003 兼容的表单模板, 在运行时进行故障排除
localization_priority: Normal
ms.assetid: 65e7882e-6397-4375-9bb4-d993d700d749
description: 以下各节介绍在使用 infopath 托管代码表单模板时可能遇到的常见故障排除方案, 这些模板使用由 SemiTrust 提供的 infopath 2003 兼容对象模型在运行时命名空间。
ms.openlocfilehash: c7b4b65cc722e72ef155529a0b2aa66c4f6cfcff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299795"
---
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-run-time"></a>在运行时使用 InfoPath 对象模型的表单模板的疑难解答

以下各节介绍了使用 infopath 托管代码表单模板时可能会遇到的常见故障排除方案, 这些模板使用的 infopath 2003 兼容对象模型由**** 运行时的 SemiTrust 命名空间。 
  
## <a name="display-notifications-for-unhandled-managed-code-exceptions-at-run-time"></a>在运行时显示未处理的托管代码异常的通知

如果在表单代码中不使用 try-catch 异常处理方法，则在调试和预览过程中，InfoPath 将在 InfoPath 错误对话框中显示有关未处理的异常的信息。 但是，默认情况下，当您部署托管代码表单模板时，未处理的异常不会在运行时显示在 InfoPath 错误对话框中。 如果您希望在运行时显示托管代码异常, 请按照[使用 InfoPath 2003 对象模型处理错误的处理程序错误](how-to-handle-errors-using-the-infopath-2003-object-model.md)的 "处理托管代码异常" 一节中的过程操作。
  
## <a name="problems-with-managed-code-form-templates-after-deployment"></a>部署后的托管代码表单模板问题

请务必在将要最终部署您的托管代码表单模板的位置测试该表单模板。 有关部署过程的信息, 请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。 有关影响部署的安全方案的信息, 请参阅[关于包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)。
  
如果您使用 .NET Framework 1.1 配置实用程序和 InfoPath 表单模板代码组来添加针对托管代码表单模板的特定权限，请确保在所有客户端计算机上部署相同的安全策略。 另外，如果您要指定引用本地计算机上某个位置的 **URLEvidence**，请确保该指定位置引用的是将最终部署解决方案的文件夹（而不是开发过程中使用的位置）。 有关为托管代码表单模板配置 .net Framework 安全设置的信息, 请参阅为[表单模板配置安全设置](how-to-configure-security-settings-for-form-templates-with-code.md)主题中的 "将 FullTrust 分配给特定 URL 或 UNC 的表单" 一节。 
  
## <a name="see-also"></a>另请参阅

- [关于包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
- [部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)
- [使用 InfoPath 2003 对象模型处理错误](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [使用 InfoPath 2003 对象模型调试 InfoPath 项目](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)

