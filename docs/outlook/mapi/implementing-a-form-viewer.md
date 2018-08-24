---
title: 实现表单查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a567185c-bd72-4307-928c-08cac5494c1a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad0da261b3059ca83f2d547c25a508ec9337aa72
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584742"
---
# <a name="implementing-a-form-viewer"></a><span data-ttu-id="604f6-103">实现表单查看器</span><span class="sxs-lookup"><span data-stu-id="604f6-103">Implementing a Form Viewer</span></span>

  
  
<span data-ttu-id="604f6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="604f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="604f6-105">表单查看器包括三个对象： 消息网站视图告知接收器和了视图上下文。</span><span class="sxs-lookup"><span data-stu-id="604f6-105">A form viewer includes three objects: a message site, a view advise sink, and a view context.</span></span> <span data-ttu-id="604f6-106">每个对象，可以与窗体服务器和其表单进行交互。</span><span class="sxs-lookup"><span data-stu-id="604f6-106">Each of these objects allows you to interact with a form server and its forms.</span></span>
  
<span data-ttu-id="604f6-107">消息网站是实现的对象[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口，并可帮助您与任务，如移动、 保存或删除邮件、 创建新的邮件，或启动新表单服务器表单服务器。</span><span class="sxs-lookup"><span data-stu-id="604f6-107">A message site is an object that implements the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface and assists form servers with tasks such as moving, saving, or deleting messages, creating new messages, or launching new form servers.</span></span> <span data-ttu-id="604f6-108">消息网站使用窗体来获取有关您的客户端与各种服务提供商的状态信息。</span><span class="sxs-lookup"><span data-stu-id="604f6-108">Message sites are used by forms to get information about your client's status with respect to various service providers.</span></span> <span data-ttu-id="604f6-109">例如，窗体可用于您的消息网站获得到您当前的消息存储、 一条消息或文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="604f6-109">For example, a form can use your message site to get a pointer to your current message store, a message, or a folder.</span></span> 
  
<span data-ttu-id="604f6-110">有两种类型的**IMAPIMessageSite**接口中的方法：</span><span class="sxs-lookup"><span data-stu-id="604f6-110">There are two types of methods in the **IMAPIMessageSite** interface:</span></span> 
  
- <span data-ttu-id="604f6-111">向表单对象提供的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="604f6-111">Methods that provide information to form objects.</span></span>
    
- <span data-ttu-id="604f6-112">操作的邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="604f6-112">Methods that manipulate messages.</span></span>
    
<span data-ttu-id="604f6-113">向表单对象提供的信息的方法是实现简单。</span><span class="sxs-lookup"><span data-stu-id="604f6-113">The methods that provide information to form objects are straightforward to implement.</span></span> <span data-ttu-id="604f6-114">除[IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md)所有情况下，您应该已经可用所需的每种方法的信息。</span><span class="sxs-lookup"><span data-stu-id="604f6-114">In all cases except [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md), you should already have available the information required by each method.</span></span>
  
<span data-ttu-id="604f6-115">操作的邮件的方法应就像它们具有通过常规用户界面触发。</span><span class="sxs-lookup"><span data-stu-id="604f6-115">The methods that manipulate messages should act as if they had been triggered through your regular user interface.</span></span> <span data-ttu-id="604f6-116">例如，如果窗体对象调用[IMAPIMessageSite::NewMessage](imapimessagesite-newmessage.md)方法的行为就好像用户已选择撰写使用常规用户界面的新自定义消息。</span><span class="sxs-lookup"><span data-stu-id="604f6-116">For example, if a form object calls your [IMAPIMessageSite::NewMessage](imapimessagesite-newmessage.md) method, behave as if the user had chosen to compose a new custom message with your regular user interface.</span></span> <span data-ttu-id="604f6-117">这通常生成此行为的命令的**撰写**、**打开**、**答复**、**给所有收件人的答复**和**转发**。</span><span class="sxs-lookup"><span data-stu-id="604f6-117">Commands which typically generate this behavior are **Compose**, **Open**, **Reply**, **Reply to All Recipients**, and **Forward**.</span></span> 
  
<span data-ttu-id="604f6-118">了视图上下文是实现的对象[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口，并为当前消息，使服务器能够轻松地切换到文件夹中的下一个或上一个邮件窗体服务器提供与上下文。</span><span class="sxs-lookup"><span data-stu-id="604f6-118">A view context is an object that implements the [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md) interface and provides form servers with a context for the current message, allowing servers to easily switch to the next or previous message in the folder.</span></span> <span data-ttu-id="604f6-119">窗体使用了视图上下文的共享信息。</span><span class="sxs-lookup"><span data-stu-id="604f6-119">A form uses a view context for sharing information.</span></span> <span data-ttu-id="604f6-120">与视图上下文对象，窗体可以：</span><span class="sxs-lookup"><span data-stu-id="604f6-120">With a view context object, a form can:</span></span> 
  
- <span data-ttu-id="604f6-121">注册您的客户端的通知。</span><span class="sxs-lookup"><span data-stu-id="604f6-121">Register with your client for notifications.</span></span>
    
- <span data-ttu-id="604f6-122">激活下一个或上一个邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="604f6-122">Activate the next or previous message in the folder.</span></span>
    
- <span data-ttu-id="604f6-123">获取打印的信息。</span><span class="sxs-lookup"><span data-stu-id="604f6-123">Get printing information.</span></span>
    
- <span data-ttu-id="604f6-124">获取客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="604f6-124">Get your client's status.</span></span>
    
- <span data-ttu-id="604f6-125">获取一个流，可用于保存一条消息的文本版本。</span><span class="sxs-lookup"><span data-stu-id="604f6-125">Get a stream that can be used to save the text version of a message.</span></span>
    
<span data-ttu-id="604f6-126">类似于中的方法[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口， **IMAPIViewContext**中的方法将与用户操作和与视图上下文相关的客户端功能相关联。</span><span class="sxs-lookup"><span data-stu-id="604f6-126">Similar to the methods in the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface, the methods in **IMAPIViewContext** correlate with user actions and client features that relate to the view context.</span></span> <span data-ttu-id="604f6-127">例如，了视图上下文涉及与激活下一个或上一条消息、 排序的文件夹，内容和筛选文件夹中的内容。</span><span class="sxs-lookup"><span data-stu-id="604f6-127">For example, a view context is involved with activating the next or previous message, sorting the contents of the folder, and filtering the contents of the folder.</span></span> 
  
<span data-ttu-id="604f6-128">它并不重要的用户提供哪种机制要激活这些功能，请务必仅这些功能的语义映射到**IMAPIViewContext**接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="604f6-128">It is not important what mechanism you provide for users to activate these features, it is only important that the semantics of those features map well to the methods in the **IMAPIViewContext** interface.</span></span> 
  
<span data-ttu-id="604f6-129">查看建议接收器是实现的对象[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)从影响您查看器和帮助表单和表单查看器协同工作的窗体服务器的接口和处理通知。</span><span class="sxs-lookup"><span data-stu-id="604f6-129">A view advise sink is an object that implements the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface and handles notifications from form servers that affect your viewer and help forms and form viewers to work together.</span></span> <span data-ttu-id="604f6-130">有关详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="604f6-130">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span> 
  

