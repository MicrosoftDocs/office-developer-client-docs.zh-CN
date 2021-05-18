---
title: 预览和调试需要完全信任的表单模板
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- debugging [infopath 2007], infopath 2003-compatible form templates,previewing InfoPath 2003-compatible form templates,form templates [InfoPath 2007], previewing 2003-compatible,form templates [InfoPath 2007], debugging 2003-compatible,debugging InfoPath 2003-compatible form templates
localization_priority: Normal
ms.assetid: 5c491666-06f0-42ec-967e-1c70cd5e03a0
description: 默认情况下，如果您尝试调试或预览的托管代码项目所包含的代码调用需要完全信任的对象模型成员（例如 LoginName 属性，它需要访问有关用户登录域的信息），Microsoft InfoPath 将显示下列错误消息。
ms.openlocfilehash: 0780db286e2ca9cef381c2d24cb621c7c243dcb7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411258"
---
# <a name="preview-and-debug-form-templates-that-require-full-trust"></a><span data-ttu-id="39f06-104">预览和调试需要完全信任的表单模板</span><span class="sxs-lookup"><span data-stu-id="39f06-104">Preview and Debug Form Templates that Require Full Trust</span></span>

<span data-ttu-id="39f06-105">默认情况下，如果您尝试调试或预览的托管代码项目所包含的代码调用需要完全信任的对象模型成员（例如 **LoginName** 属性，它需要访问有关用户登录域的信息），Microsoft InfoPath 将显示下列错误消息。</span><span class="sxs-lookup"><span data-stu-id="39f06-105">By default, if you attempt to debug or preview a managed-code project that contains code that invokes an object model member that requires full trust, such as the **LoginName** property which requires access to information about the user's login domain, Microsoft InfoPath will display the following error messages.</span></span> 
  
<span data-ttu-id="39f06-106">预览时：</span><span class="sxs-lookup"><span data-stu-id="39f06-106">When previewing:</span></span>
  
<span data-ttu-id="39f06-p101">"表单代码中发生未处理的例外项"。接着将显示"由于该表单的代码中存在错误，InfoPath 无法完成此操作。"。</span><span class="sxs-lookup"><span data-stu-id="39f06-p101">"An unhandled exception has occurred in the form's code." Followed by, "InfoPath cannot complete this action, because of an error in the form's code."</span></span>
  
<span data-ttu-id="39f06-109">调试时：</span><span class="sxs-lookup"><span data-stu-id="39f06-109">When debugging:</span></span>
  
<span data-ttu-id="39f06-110">焦点将移至代码编辑器中调用需要完全信任的成员的代码行，并将显示以下消息：" **SecurityException** 未由用户代码进行处理 - 请求失败"。</span><span class="sxs-lookup"><span data-stu-id="39f06-110">Focus will move to the line of code in the code editor that is calling the member that requires full trust, and the following message will be displayed: " **SecurityException** was unhandled by user code - Request failed".</span></span> 
  
<span data-ttu-id="39f06-111">要在调试或预览时允许表单模板的业务逻辑调用此成员，您必须按照下面的过程将表单模板的安全级别设为“完全信任”。</span><span class="sxs-lookup"><span data-stu-id="39f06-111">To allow the form template's business logic to call this member when it is being debugged or previewed, you must set your form template's security level to **Full Trust** as described in the following procedure.</span></span> 
  
## <a name="configuring-a-managed-code-form-template-that-requires-full-trust"></a><span data-ttu-id="39f06-112">配置需要完全信任的托管代码表单模板</span><span class="sxs-lookup"><span data-stu-id="39f06-112">Configuring a Managed Code Form Template that Requires Full Trust</span></span>

### <a name="set-your-forms-security-level-to-full-trust"></a><span data-ttu-id="39f06-113">将表单的安全级别设为"完全信任"</span><span class="sxs-lookup"><span data-stu-id="39f06-113">Set your form's security level to Full Trust</span></span>

1. <span data-ttu-id="39f06-114">在 InfoPath 中，在设计模式下打开表单模板。</span><span class="sxs-lookup"><span data-stu-id="39f06-114">In InfoPath, open the form template in design mode.</span></span>
    
2. <span data-ttu-id="39f06-115">单击“文件”选项卡，然后单击“信息”选项卡上的“表单选项”。</span><span class="sxs-lookup"><span data-stu-id="39f06-115">Click the **File** tab, and then click **Form Options** on the **Info** tab.</span></span> 
    
3. <span data-ttu-id="39f06-116">在“类别”列表中，单击“安全和信任”。</span><span class="sxs-lookup"><span data-stu-id="39f06-116">In the **Category** list, click **Security and Trust.**</span></span>
    
4. <span data-ttu-id="39f06-117">在“安全级别”下，清除“自动确定安全级别”。</span><span class="sxs-lookup"><span data-stu-id="39f06-117">Under **Security Level**, clear **Automatically determine security level**.</span></span>
    
5. <span data-ttu-id="39f06-118">选择“完全信任”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="39f06-118">Select **Full Trust**, and then click **OK**.</span></span>
    
<span data-ttu-id="39f06-119">执行此过程后，您便可以按照[预览和调试包含代码的 InfoPath 表单模板](how-to-preview-and-debug-infopath-form-templates-with-code.md)中介绍的那样来调试项目了。</span><span class="sxs-lookup"><span data-stu-id="39f06-119">After this procedure is performed, you can debug your project as described in [Preview and Debug InfoPath Form Templates with Code](how-to-preview-and-debug-infopath-form-templates-with-code.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="39f06-120">要成功部署需要完全信任的托管代码表单模板，还需要执行其他一些步骤，例如进行数字签名或安装并注册表单模板。</span><span class="sxs-lookup"><span data-stu-id="39f06-120">Successfully deploying a managed code form template that requires full trust requires additional steps, such as digitally signing, or installing and registering the form template.</span></span> <span data-ttu-id="39f06-121">有关在调试后部署托管代码表单模板的信息，请参阅[部署包含代码的 InfoPath 表单模板](how-to-deploy-infopath-form-templates-with-code.md)。</span><span class="sxs-lookup"><span data-stu-id="39f06-121">For information on deploying a managed code form template after it is debugged see, [Deploy InfoPath Form Templates with Code](how-to-deploy-infopath-form-templates-with-code.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="39f06-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39f06-122">See also</span></span>



[<span data-ttu-id="39f06-123">预览和调试包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="39f06-123">Preview and Debug InfoPath Form Templates with Code</span></span>](how-to-preview-and-debug-infopath-form-templates-with-code.md)
  
[<span data-ttu-id="39f06-124">部署包含代码的 InfoPath 表单模板</span><span class="sxs-lookup"><span data-stu-id="39f06-124">Deploy InfoPath Form Templates with Code</span></span>](how-to-deploy-infopath-form-templates-with-code.md)

