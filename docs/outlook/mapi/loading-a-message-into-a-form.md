---
title: 将一条消息加载到窗体
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4bdbe021-d694-4967-a105-4b24f1eebc44
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d677958b1a429201c05b5195c58bd7462d0f3d37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776146"
---
# <a name="loading-a-message-into-a-form"></a><span data-ttu-id="9c6c4-103">将一条消息加载到窗体</span><span class="sxs-lookup"><span data-stu-id="9c6c4-103">Loading a Message Into a Form</span></span>

  
  
<span data-ttu-id="9c6c4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9c6c4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9c6c4-105">若要使用表单服务器表单加载现有消息，请使用以下策略之一。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-105">To load an existing message into a form using a form server, use one of the following strategies.</span></span>
  
- <span data-ttu-id="9c6c4-106">调用[IMAPISession::PrepareForm](imapisession-prepareform.md)创建令牌，然后[IMAPISession::ShowForm](imapisession-showform.md)显示窗体。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-106">Call [IMAPISession::PrepareForm](imapisession-prepareform.md) to create a token and then [IMAPISession::ShowForm](imapisession-showform.md) to display the form.</span></span> 
    
- <span data-ttu-id="9c6c4-107">调用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-107">Call [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md).</span></span> 
    
<span data-ttu-id="9c6c4-108">使用的**PrepareForm**和**ShowForm**策略而言容易，但其结果是相对于您的客户端模式的窗体中。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-108">Using the **PrepareForm** and **ShowForm** strategy is comparatively easy, but it results in forms that are modal with respect to your client.</span></span> <span data-ttu-id="9c6c4-109">这是因为**ShowForm**将呼叫不会返回直到窗体已退出。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-109">This is because the call to **ShowForm** does not return until the form has exited.</span></span> <span data-ttu-id="9c6c4-110">如果您需要异步处理窗体，请不要使用此策略。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-110">If you need to handle forms asynchronously, do not use this strategy.</span></span> 
  
<span data-ttu-id="9c6c4-111">使用**LoadForm**策略是更加难以，因为方法需要多个参数。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-111">Using the **LoadForm** strategy is more difficult because the method requires several parameters.</span></span> <span data-ttu-id="9c6c4-112">这些参数指示窗体管理器启动正确的上下文中的正确表单服务器并显示正确的消息。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-112">These parameters instruct the form manager to launch the proper form server in the proper context and display the proper message.</span></span> <span data-ttu-id="9c6c4-113">如果已运行窗体服务器，窗体管理器将加载邮件到窗体服务器无需启动的窗体服务器的新实例。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-113">If the form server is already running, the form manager loads the message into the form server without launching a new instance of the form server.</span></span> 
  
<span data-ttu-id="9c6c4-114">指定要启动，则传递的邮件类的窗体服务器处理_lpszMessageClass_参数的内容中的目标服务器。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-114">To specify which form server to launch, pass the message class handled by the target server in the contents of the  _lpszMessageClass_ parameter.</span></span> <span data-ttu-id="9c6c4-115">可以通过检索邮件要加载的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性确定适当的邮件类。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-115">The appropriate message class can be determined by retrieving the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the message to be loaded.</span></span> <span data-ttu-id="9c6c4-116">有时没有窗体服务器指定的邮件类仅窗体服务器的处理属于消息的超类别的邮件。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-116">Sometimes there is no form server for the specified message class, only a form server that handles messages belonging to the message's superclass.</span></span> <span data-ttu-id="9c6c4-117">如果您愿意加载只能通过专门为了处理邮件的类的窗体服务器的邮件，，设置 MAPIFORM_EXACTMATCH 标志**LoadForm**呼叫中。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-117">If you prefer that the message be loaded only by a form server specifically meant to handle messages of that class, set the MAPIFORM_EXACTMATCH flag in the **LoadForm** call.</span></span> <span data-ttu-id="9c6c4-118">有关详细信息，请参阅[MAPI 邮件类](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-118">For more information, see [MAPI Message Classes](mapi-message-classes.md).</span></span>
  
 <span data-ttu-id="9c6c4-119">**LoadForm**还需要为查看者的消息网站和视图上下文，将值的指针的目标消息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 和**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))属性。</span><span class="sxs-lookup"><span data-stu-id="9c6c4-119">**LoadForm** also requires a pointer to your viewer's message site and view context and the value for the target message's **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) and **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) properties.</span></span>
  

