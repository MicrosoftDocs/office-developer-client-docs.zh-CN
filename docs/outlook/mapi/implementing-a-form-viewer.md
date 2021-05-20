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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435815"
---
# <a name="implementing-a-form-viewer"></a><span data-ttu-id="0ed99-103">实现表单查看器</span><span class="sxs-lookup"><span data-stu-id="0ed99-103">Implementing a Form Viewer</span></span>

  
  
<span data-ttu-id="0ed99-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ed99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ed99-105">表单查看器包括三个对象：消息网站、视图建议接收器和视图上下文。</span><span class="sxs-lookup"><span data-stu-id="0ed99-105">A form viewer includes three objects: a message site, a view advise sink, and a view context.</span></span> <span data-ttu-id="0ed99-106">其中每个对象都允许您与表单服务器及其表单进行交互。</span><span class="sxs-lookup"><span data-stu-id="0ed99-106">Each of these objects allows you to interact with a form server and its forms.</span></span>
  
<span data-ttu-id="0ed99-107">消息网站是一个实现 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口的对象，可帮助表单服务器执行移动、保存或删除消息、创建新消息或启动新表单服务器等任务。</span><span class="sxs-lookup"><span data-stu-id="0ed99-107">A message site is an object that implements the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface and assists form servers with tasks such as moving, saving, or deleting messages, creating new messages, or launching new form servers.</span></span> <span data-ttu-id="0ed99-108">邮件网站由表单用于获取有关各种服务提供商的客户端状态的信息。</span><span class="sxs-lookup"><span data-stu-id="0ed99-108">Message sites are used by forms to get information about your client's status with respect to various service providers.</span></span> <span data-ttu-id="0ed99-109">例如，窗体可以使用邮件网站获取指向当前邮件存储、邮件或文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="0ed99-109">For example, a form can use your message site to get a pointer to your current message store, a message, or a folder.</span></span> 
  
<span data-ttu-id="0ed99-110">**IMAPIMessageSite** 接口有两种类型的方法：</span><span class="sxs-lookup"><span data-stu-id="0ed99-110">There are two types of methods in the **IMAPIMessageSite** interface:</span></span> 
  
- <span data-ttu-id="0ed99-111">向表单对象提供信息的方法。</span><span class="sxs-lookup"><span data-stu-id="0ed99-111">Methods that provide information to form objects.</span></span>
    
- <span data-ttu-id="0ed99-112">操作邮件的方法。</span><span class="sxs-lookup"><span data-stu-id="0ed99-112">Methods that manipulate messages.</span></span>
    
<span data-ttu-id="0ed99-113">向表单对象提供信息的方法很容易实现。</span><span class="sxs-lookup"><span data-stu-id="0ed99-113">The methods that provide information to form objects are straightforward to implement.</span></span> <span data-ttu-id="0ed99-114">在除 [IMAPIMessageSite：：GetSiteStatus](imapimessagesite-getsitestatus.md)之外的所有情况下，都应已提供每个方法所需的信息。</span><span class="sxs-lookup"><span data-stu-id="0ed99-114">In all cases except [IMAPIMessageSite::GetSiteStatus](imapimessagesite-getsitestatus.md), you should already have available the information required by each method.</span></span>
  
<span data-ttu-id="0ed99-115">操作消息的方法应像通过常规用户界面触发一样操作。</span><span class="sxs-lookup"><span data-stu-id="0ed99-115">The methods that manipulate messages should act as if they had been triggered through your regular user interface.</span></span> <span data-ttu-id="0ed99-116">例如，如果表单对象调用 [IMAPIMessageSite：：NewMessage](imapimessagesite-newmessage.md) 方法，则其行为就像用户已选择使用常规用户界面撰写新的自定义邮件一样。</span><span class="sxs-lookup"><span data-stu-id="0ed99-116">For example, if a form object calls your [IMAPIMessageSite::NewMessage](imapimessagesite-newmessage.md) method, behave as if the user had chosen to compose a new custom message with your regular user interface.</span></span> <span data-ttu-id="0ed99-117">通常生成此行为的命令有Compose、Open、Reply、Reply **to All Recipients** 和 **Forward**。  </span><span class="sxs-lookup"><span data-stu-id="0ed99-117">Commands which typically generate this behavior are **Compose**, **Open**, **Reply**, **Reply to All Recipients**, and **Forward**.</span></span> 
  
<span data-ttu-id="0ed99-118">视图上下文是一个实现 [IMAPIViewContext ： IUnknown](imapiviewcontextiunknown.md) 接口的对象，可为表单服务器提供当前消息的上下文，从而使服务器可以轻松地切换到文件夹中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0ed99-118">A view context is an object that implements the [IMAPIViewContext : IUnknown](imapiviewcontextiunknown.md) interface and provides form servers with a context for the current message, allowing servers to easily switch to the next or previous message in the folder.</span></span> <span data-ttu-id="0ed99-119">表单使用视图上下文来共享信息。</span><span class="sxs-lookup"><span data-stu-id="0ed99-119">A form uses a view context for sharing information.</span></span> <span data-ttu-id="0ed99-120">对于视图上下文对象，表单可以：</span><span class="sxs-lookup"><span data-stu-id="0ed99-120">With a view context object, a form can:</span></span> 
  
- <span data-ttu-id="0ed99-121">在客户端中注册以接收通知。</span><span class="sxs-lookup"><span data-stu-id="0ed99-121">Register with your client for notifications.</span></span>
    
- <span data-ttu-id="0ed99-122">激活文件夹中的下一封邮件或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="0ed99-122">Activate the next or previous message in the folder.</span></span>
    
- <span data-ttu-id="0ed99-123">获取打印信息。</span><span class="sxs-lookup"><span data-stu-id="0ed99-123">Get printing information.</span></span>
    
- <span data-ttu-id="0ed99-124">获取客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="0ed99-124">Get your client's status.</span></span>
    
- <span data-ttu-id="0ed99-125">获取可用于保存邮件的文本版本的流。</span><span class="sxs-lookup"><span data-stu-id="0ed99-125">Get a stream that can be used to save the text version of a message.</span></span>
    
<span data-ttu-id="0ed99-126">与 [IMAPIMessageSite ： IUnknown](imapimessagesiteiunknown.md) 接口中的方法类似 **，IMAPIViewContext** 中的方法与与视图上下文相关的用户操作和客户端功能关联。</span><span class="sxs-lookup"><span data-stu-id="0ed99-126">Similar to the methods in the [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) interface, the methods in **IMAPIViewContext** correlate with user actions and client features that relate to the view context.</span></span> <span data-ttu-id="0ed99-127">例如，视图上下文涉及激活下一封邮件或上一封邮件、对文件夹内容进行排序以及筛选文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="0ed99-127">For example, a view context is involved with activating the next or previous message, sorting the contents of the folder, and filtering the contents of the folder.</span></span> 
  
<span data-ttu-id="0ed99-128">为用户提供哪些机制来激活这些功能并非很重要，这些功能的语义必须很好地映射到 **IMAPIViewContext** 接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="0ed99-128">It is not important what mechanism you provide for users to activate these features, it is only important that the semantics of those features map well to the methods in the **IMAPIViewContext** interface.</span></span> 
  
<span data-ttu-id="0ed99-129">视图通知接收器是一个对象，它实现 [IMAPIViewAdviseSink ： IUnknown](imapiviewadvisesinkiunknown.md) 接口，并处理来自影响查看器的表单服务器的通知，并帮助表单和表单查看器协同工作。</span><span class="sxs-lookup"><span data-stu-id="0ed99-129">A view advise sink is an object that implements the [IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md) interface and handles notifications from form servers that affect your viewer and help forms and form viewers to work together.</span></span> <span data-ttu-id="0ed99-130">有关详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="0ed99-130">For more information, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span> 
  

