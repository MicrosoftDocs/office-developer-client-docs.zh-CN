---
title: 运行时使用 InfoPath 对象模型的表单模板疑难解答
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- 表单模板疑难解答 [infopath 2007]， run time，InfoPath 2003-compatible form templates， troubleshooting at run time
localization_priority: Normal
ms.assetid: 65e7882e-6397-4375-9bb4-d993d700d749
description: 以下各节介绍使用由 Microsoft 提供的 InfoPath 2003 兼容对象模型的 InfoPath 托管代码表单模板时可能遇到的常见疑难解答方案。Office.Interop.InfoPath.SemiTrust 命名空间运行时运行。
ms.openlocfilehash: c7b4b65cc722e72ef155529a0b2aa66c4f6cfcff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414443"
---
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-run-time"></a>运行时使用 InfoPath 对象模型的表单模板疑难解答

以下各节介绍使用 InfoPath 托管代码表单模板时可能遇到的常见疑难解答方案，这些表单模板使用 **由 Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 InfoPath 2003 兼容对象模型。 
  
## <a name="display-notifications-for-unhandled-managed-code-exceptions-at-run-time"></a>显示运行时未处理托管代码异常的通知

如果在表单代码中不使用 try-catch 异常处理方法，则在调试和预览过程中，InfoPath 将在 InfoPath 错误对话框中显示有关未处理的异常的信息。 但是，默认情况下，当您部署托管代码表单模板时，未处理的异常不会在运行时显示在 InfoPath 错误对话框中。 如果希望运行时显示托管代码异常，请按照使用 [InfoPath 2003](how-to-handle-errors-using-the-infopath-2003-object-model.md)对象模型处理错误的"处理托管代码异常"部分中的过程操作。
  
## <a name="problems-with-managed-code-form-templates-after-deployment"></a>部署后托管代码表单模板的问题

请务必在将要最终部署您的托管代码表单模板的位置测试该表单模板。 有关部署过程的信息，请参阅部署包含代码的 [InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。 有关影响部署的安全方案的信息，请参阅关于包含代码的 [表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)。
  
如果您使用 .NET Framework 1.1 配置实用程序和 InfoPath 表单模板代码组来添加针对托管代码表单模板的特定权限，请确保在所有客户端计算机上部署相同的安全策略。 另外，如果您要指定引用本地计算机上某个位置的 **URLEvidence**，请确保该指定位置引用的是将最终部署解决方案的文件夹（而不是开发过程中使用的位置）。 有关为托管代码 表单模板 配置 .NET Framework 安全设置的信息，请参阅 Configure [Security 设置 for Form Templates with Code](how-to-configure-security-settings-for-form-templates-with-code.md)主题的"为位于特定 URL 或 UNC 的表单分配 FullTrust"部分。 
  
## <a name="see-also"></a>另请参阅

- [关于包含代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)
- [部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)
- [使用 InfoPath 2003 对象模型处理错误](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [使用 InfoPath 2003 对象模型调试 InfoPath 项目](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)

