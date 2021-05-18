---
title: 将邮件加载到窗体中
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bdbe021-d694-4967-a105-4b24f1eebc44
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afecd3b334dd2cf7b2953916872982e6459a8434
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412413"
---
# <a name="loading-a-message-into-a-form"></a><span data-ttu-id="2011a-103">将邮件加载到窗体中</span><span class="sxs-lookup"><span data-stu-id="2011a-103">Loading a Message Into a Form</span></span>

  
  
<span data-ttu-id="2011a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2011a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2011a-105">若要使用表单服务器将现有邮件加载到表单中，请使用以下策略之一。</span><span class="sxs-lookup"><span data-stu-id="2011a-105">To load an existing message into a form using a form server, use one of the following strategies.</span></span>
  
- <span data-ttu-id="2011a-106">调用 [IMAPISession：:P repareForm](imapisession-prepareform.md) 创建令牌，然后 [调用 IMAPISession：：ShowForm](imapisession-showform.md) 以显示表单。</span><span class="sxs-lookup"><span data-stu-id="2011a-106">Call [IMAPISession::PrepareForm](imapisession-prepareform.md) to create a token and then [IMAPISession::ShowForm](imapisession-showform.md) to display the form.</span></span> 
    
- <span data-ttu-id="2011a-107">调用 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md)。</span><span class="sxs-lookup"><span data-stu-id="2011a-107">Call [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md).</span></span> 
    
<span data-ttu-id="2011a-108">使用 **PrepareForm** 和 **ShowForm** 策略相对容易一些，但它会形成与客户端有关的模式表单。</span><span class="sxs-lookup"><span data-stu-id="2011a-108">Using the **PrepareForm** and **ShowForm** strategy is comparatively easy, but it results in forms that are modal with respect to your client.</span></span> <span data-ttu-id="2011a-109">这是因为，在退出窗体之前， **对 ShowForm** 的调用不会返回。</span><span class="sxs-lookup"><span data-stu-id="2011a-109">This is because the call to **ShowForm** does not return until the form has exited.</span></span> <span data-ttu-id="2011a-110">如果需要异步处理表单，请不要使用此策略。</span><span class="sxs-lookup"><span data-stu-id="2011a-110">If you need to handle forms asynchronously, do not use this strategy.</span></span> 
  
<span data-ttu-id="2011a-111">使用 **LoadForm** 策略更加困难，因为该方法需要多个参数。</span><span class="sxs-lookup"><span data-stu-id="2011a-111">Using the **LoadForm** strategy is more difficult because the method requires several parameters.</span></span> <span data-ttu-id="2011a-112">这些参数指示表单管理器在正确的上下文中启动正确的表单服务器并显示正确的消息。</span><span class="sxs-lookup"><span data-stu-id="2011a-112">These parameters instruct the form manager to launch the proper form server in the proper context and display the proper message.</span></span> <span data-ttu-id="2011a-113">如果表单服务器已在运行，则表单管理器将邮件加载至表单服务器，而无需启动表单服务器的新实例。</span><span class="sxs-lookup"><span data-stu-id="2011a-113">If the form server is already running, the form manager loads the message into the form server without launching a new instance of the form server.</span></span> 
  
<span data-ttu-id="2011a-114">若要指定要启动的表单服务器，在  _lpszMessageClass_ 参数的内容中传递由目标服务器处理的邮件类。</span><span class="sxs-lookup"><span data-stu-id="2011a-114">To specify which form server to launch, pass the message class handled by the target server in the contents of the  _lpszMessageClass_ parameter.</span></span> <span data-ttu-id="2011a-115">可以通过检索要加载的邮件的[PidTagMessageClass PR_MESSAGE_CLASS (PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性来确定相应的邮件类。 </span><span class="sxs-lookup"><span data-stu-id="2011a-115">The appropriate message class can be determined by retrieving the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message to be loaded.</span></span> <span data-ttu-id="2011a-116">有时，没有用于指定邮件类的窗体服务器，只有一个处理属于邮件的超级类的邮件的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="2011a-116">Sometimes there is no form server for the specified message class, only a form server that handles messages belonging to the message's superclass.</span></span> <span data-ttu-id="2011a-117">如果您希望邮件仅由专门用来处理该类的邮件的窗体服务器加载，请设置 **LoadForm** 调用中的 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="2011a-117">If you prefer that the message be loaded only by a form server specifically meant to handle messages of that class, set the MAPIFORM_EXACTMATCH flag in the **LoadForm** call.</span></span> <span data-ttu-id="2011a-118">有关详细信息，请参阅 [MAPI Message Classes](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="2011a-118">For more information, see [MAPI Message Classes](mapi-message-classes.md).</span></span>
  
 <span data-ttu-id="2011a-119">**LoadForm** 还需要一个指向查看者的邮件网站和视图上下文的指针，以及目标邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 和 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="2011a-119">**LoadForm** also requires a pointer to your viewer's message site and view context and the value for the target message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) and **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) properties.</span></span>
  

