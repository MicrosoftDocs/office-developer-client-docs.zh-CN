---
title: 解决在运行时使用 InfoPath 对象模型的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- troubleshooting form templates [infopath 2007], run time,InfoPath 2003-compatible form templates, troubleshooting at run time
localization_priority: Normal
ms.assetid: 65e7882e-6397-4375-9bb4-d993d700d749
description: 以下各节描述了当您使用 InfoPath 托管代码表单模板（这些模板在运行时使用由 Microsoft.Office.Interop.InfoPath.SemiTrust 命名空间提供的 InfoPath 2003 兼容对象模型）时可能遇到的常见问题及解答。
ms.openlocfilehash: 8c83679a0cd61fae212b3143b6b0131da92ac7f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774091"
---
# <a name="troubleshoot-form-templates-that-use-the-infopath-object-model-at-run-time"></a><span data-ttu-id="8f503-104">解决在运行时使用 InfoPath 对象模型的表单模板</span><span class="sxs-lookup"><span data-stu-id="8f503-104">Troubleshoot form templates that use the InfoPath object model at run time</span></span>

<span data-ttu-id="8f503-105">以下各节描述了当您使用 InfoPath 托管代码表单模板（这些模板在运行时使用由 **Microsoft.Office.Interop.InfoPath.SemiTrust** 命名空间提供的 InfoPath 2003 兼容对象模型）时可能遇到的常见问题及解答。</span><span class="sxs-lookup"><span data-stu-id="8f503-105">The following sections describe common troubleshooting scenarios you may encounter while working with InfoPath managed-code form templates that use the InfoPath 2003-compatible object model provided by the **Microsoft.Office.Interop.InfoPath.SemiTrust** namespace at run time.</span></span> 
  
## <a name="display-notifications-for-unhandled-managed-code-exceptions-at-run-time"></a><span data-ttu-id="8f503-106">在运行时显示的通知的未处理的托管代码异常</span><span class="sxs-lookup"><span data-stu-id="8f503-106">Display notifications for unhandled managed-code exceptions at run time</span></span>

<span data-ttu-id="8f503-107">如果在表单代码中不使用 try-catch 异常处理方法，则在调试和预览过程中，InfoPath 将在 InfoPath 错误对话框中显示有关未处理的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="8f503-107">If you do not use try-catch exception handling in your form code, InfoPath will display information about unhandled exceptions in the InfoPath error dialog box while debugging and previewing.</span></span> <span data-ttu-id="8f503-108">但是，默认情况下，当您部署托管代码表单模板时，未处理的异常不会在运行时显示在 InfoPath 错误对话框中。</span><span class="sxs-lookup"><span data-stu-id="8f503-108">However, by default, unhandled exceptions are not displayed in the InfoPath error dialog box at run time when you deploy your managed-code form template.</span></span> <span data-ttu-id="8f503-109">如果您希望在运行时显示的托管代码异常，按照[处理错误使用 InfoPath 2003 对象模型](how-to-handle-errors-using-the-infopath-2003-object-model.md)的"处理托管代码异常"部分中的过程。</span><span class="sxs-lookup"><span data-stu-id="8f503-109">If you want managed-code exceptions displayed at run time, follow the procedure in the "Handling Managed Code Exceptions" section of [Handle Errors Using the InfoPath 2003 Object Model](how-to-handle-errors-using-the-infopath-2003-object-model.md).</span></span>
  
## <a name="problems-with-managed-code-form-templates-after-deployment"></a><span data-ttu-id="8f503-110">部署后托管代码表单模板的问题</span><span class="sxs-lookup"><span data-stu-id="8f503-110">Problems with managed-code form templates after deployment</span></span>

<span data-ttu-id="8f503-111">请务必在将要最终部署您的托管代码表单模板的位置测试该表单模板。</span><span class="sxs-lookup"><span data-stu-id="8f503-111">Be sure to test your managed-code form template in the location where it will be finally deployed.</span></span> <span data-ttu-id="8f503-112">有关部署过程的信息，请参阅[替换代码中部署 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="8f503-112">For information on deployment procedures, see [Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span> <span data-ttu-id="8f503-113">有关影响部署的安全方案的信息，请参阅[关于具有代码的表单模板的安全模型](about-the-security-model-for-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="8f503-113">For information on security scenarios that affect deployment, see [About the Security Model for Form Templates with Code](about-the-security-model-for-form-templates-with-code.md).</span></span>
  
<span data-ttu-id="8f503-114">如果您使用 .NET Framework 1.1 配置实用程序和 InfoPath 表单模板代码组来添加针对托管代码表单模板的特定权限，请确保在所有客户端计算机上部署相同的安全策略。</span><span class="sxs-lookup"><span data-stu-id="8f503-114">If you use the .NET Framework 1.1 Configuration utility and the InfoPath Form Templates code group to add specific permissions for a managed-code form template, make sure that the same security policy is deployed on all client computers.</span></span> <span data-ttu-id="8f503-115">另外，如果您要指定引用本地计算机上某个位置的 **URLEvidence**，请确保该指定位置引用的是将最终部署解决方案的文件夹（而不是开发过程中使用的位置）。</span><span class="sxs-lookup"><span data-stu-id="8f503-115">Also, if you are specifying **URLEvidence** that refers to a location on the local computer, make sure that the specified location refers to the folder where the solution will be finally deployed (not the same location used during development).</span></span> <span data-ttu-id="8f503-116">配置托管代码表单模板的.NET Framework 安全设置的信息，请参阅[为包含代码的表单模板配置安全设置](how-to-configure-security-settings-for-form-templates-with-code.md)主题的"分配 FullTrust 到窗体位于特定 URL 或 UNC"部分。</span><span class="sxs-lookup"><span data-stu-id="8f503-116">For information on configuring .NET Framework security settings for a managed-code form template, see the "Assigning FullTrust to Forms at a Specific URL or UNC" section of the [Configure Security Settings for Form Templates with Code](how-to-configure-security-settings-for-form-templates-with-code.md) topic.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8f503-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f503-117">See also</span></span>

- [<span data-ttu-id="8f503-118">关于具有代码的表单模板的安全模型</span><span class="sxs-lookup"><span data-stu-id="8f503-118">About the Security Model for Form Templates with Code</span></span>](about-the-security-model-for-form-templates-with-code.md)
- [<span data-ttu-id="8f503-119">部署包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="8f503-119">Deploy InfoPath Form Templates with Code</span></span>](how-to-deploy-infopath-form-templates-with-code.md)
- [<span data-ttu-id="8f503-120">使用 InfoPath 2003 对象模型处理错误</span><span class="sxs-lookup"><span data-stu-id="8f503-120">Handle Errors Using the InfoPath 2003 Object Model</span></span>](how-to-handle-errors-using-the-infopath-2003-object-model.md)
- [<span data-ttu-id="8f503-121">调试使用 InfoPath 2003 对象模型的 InfoPath 项目</span><span class="sxs-lookup"><span data-stu-id="8f503-121">Debug InfoPath Projects Using the InfoPath 2003 Object Model</span></span>](how-to-debug-infopath-projects-using-the-infopath-2003-object-model.md)
