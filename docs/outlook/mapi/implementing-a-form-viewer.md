---
title: 实现表单查看器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a567185c-bd72-4307-928c-08cac5494c1a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bbd0792b0e3e3f274797fabd7f5d5eb49cfc73fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332891"
---
# <a name="implementing-a-form-viewer"></a><span data-ttu-id="d0ef3-103">实现表单查看器</span><span class="sxs-lookup"><span data-stu-id="d0ef3-103">Implementing a Form Viewer</span></span>

  
  
<span data-ttu-id="d0ef3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d0ef3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d0ef3-105">表单查看器包括三个对象: 邮件网站、视图通知接收器和视图上下文。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-105">A form viewer includes three objects: a message site, a view advise sink, and a view context.</span></span> <span data-ttu-id="d0ef3-106">这些对象中的每一个都允许您与表单服务器及其表单进行交互。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-106">Each of these objects allows you to interact with a form server and its forms.</span></span>
  
<span data-ttu-id="d0ef3-107">邮件站点是一个对象, 它实现[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口, 并协助表单服务器处理包含移动、保存或删除邮件、创建新邮件或启动新表单服务器等任务的任务。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-107">A message site is an object that implements the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface and assists form servers with tasks such as moving, saving, or deleting messages, creating new messages, or launching new form servers.</span></span> <span data-ttu-id="d0ef3-108">表单使用消息网站获取有关有关各种服务提供商的客户端状态信息。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-108">Message sites are used by forms to get information about your client's status with respect to various service providers.</span></span> <span data-ttu-id="d0ef3-109">例如, 窗体可以使用您的邮件网站获取指向当前邮件存储、邮件或文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-109">For example, a form can use your message site to get a pointer to your current message store, a message, or a folder.</span></span> 
  
<span data-ttu-id="d0ef3-110">**IMAPIMessageSite**接口中有两种类型的方法:</span><span class="sxs-lookup"><span data-stu-id="d0ef3-110">There are two types of methods in the **IMAPIMessageSite** interface:</span></span> 
  
- <span data-ttu-id="d0ef3-111">向表单对象提供信息的方法。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-111">Methods that provide information to form objects.</span></span>
    
- <span data-ttu-id="d0ef3-112">操作邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-112">Methods that manipulate messages.</span></span>
    
<span data-ttu-id="d0ef3-113">向表单对象提供信息的方法是实现简单的。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-113">The methods that provide information to form objects are straightforward to implement.</span></span> <span data-ttu-id="d0ef3-114">在除[IMAPIMessageSite:: GetSiteStatus](imapimessagesite-getsitestatus.md)之外的所有情况下, 您应该已经有了每种方法所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-114">In all cases except [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md), you should already have available the information required by each method.</span></span>
  
<span data-ttu-id="d0ef3-115">操作邮件的方法应类似于通过常规用户界面触发的方法。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-115">The methods that manipulate messages should act as if they had been triggered through your regular user interface.</span></span> <span data-ttu-id="d0ef3-116">例如, 如果 form 对象调用您的[IMAPIMessageSite:: NewMessage](imapimessagesite-newmessage.md)方法, 则行为与用户选择使用常规用户界面撰写新的自定义邮件的行为相同。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-116">For example, if a form object calls your [IMAPIMessageSite::NewMessage](imapimessagesite-newmessage.md) method, behave as if the user had chosen to compose a new custom message with your regular user interface.</span></span> <span data-ttu-id="d0ef3-117">通常会生成此行为的命令包括**撰写**、**打开**、**答复**、**答复所有收件人**和**转发**。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-117">Commands which typically generate this behavior are **Compose**, **Open**, **Reply**, **Reply to All Recipients**, and **Forward**.</span></span> 
  
<span data-ttu-id="d0ef3-118">view context 是一个实现[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)接口的对象, 它提供具有当前邮件的上下文的表单服务器, 使服务器可以轻松地切换到文件夹中的下一封或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-118">A view context is an object that implements the [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md) interface and provides form servers with a context for the current message, allowing servers to easily switch to the next or previous message in the folder.</span></span> <span data-ttu-id="d0ef3-119">表单使用视图上下文来共享信息。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-119">A form uses a view context for sharing information.</span></span> <span data-ttu-id="d0ef3-120">使用 view context 对象, 窗体可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d0ef3-120">With a view context object, a form can:</span></span> 
  
- <span data-ttu-id="d0ef3-121">向客户端注册以获取通知。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-121">Register with your client for notifications.</span></span>
    
- <span data-ttu-id="d0ef3-122">激活文件夹中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-122">Activate the next or previous message in the folder.</span></span>
    
- <span data-ttu-id="d0ef3-123">获取打印信息。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-123">Get printing information.</span></span>
    
- <span data-ttu-id="d0ef3-124">获取客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-124">Get your client's status.</span></span>
    
- <span data-ttu-id="d0ef3-125">获取可用于保存邮件文本版本的流。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-125">Get a stream that can be used to save the text version of a message.</span></span>
    
<span data-ttu-id="d0ef3-126">与[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)接口中的方法类似, **IMAPIViewContext**中的方法与与视图上下文相关的用户操作和客户端功能相关联。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-126">Similar to the methods in the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface, the methods in **IMAPIViewContext** correlate with user actions and client features that relate to the view context.</span></span> <span data-ttu-id="d0ef3-127">例如, 激活下一条或上一封邮件、对文件夹内容进行排序以及筛选该文件夹的内容, 都涉及视图上下文。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-127">For example, a view context is involved with activating the next or previous message, sorting the contents of the folder, and filtering the contents of the folder.</span></span> 
  
<span data-ttu-id="d0ef3-128">为用户提供的用于激活这些功能的机制并不重要, 仅重要的是这些功能的语义能够很好地映射到**IMAPIViewContext**接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-128">It is not important what mechanism you provide for users to activate these features, it is only important that the semantics of those features map well to the methods in the **IMAPIViewContext** interface.</span></span> 
  
<span data-ttu-id="d0ef3-129">视图建议接收器是一个实现[IMAPIViewAdviseSink: IUnknown](imapiviewadvisesinkiunknown.md)接口的对象, 并处理来自影响您的查看器和帮助表单和表单查看器协同工作的表单服务器的通知。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-129">A view advise sink is an object that implements the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface and handles notifications from form servers that affect your viewer and help forms and form viewers to work together.</span></span> <span data-ttu-id="d0ef3-130">有关详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ef3-130">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span> 
  

