---
title: IMAPIMessageSite IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite
api_type:
- COM
ms.assetid: 883448f5-0d3f-486d-80a3-7b961c209cd0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bf21ed1d41a61f600cfded777b699cf620c2e00f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433365"
---
# <a name="imapimessagesite--iunknown"></a><span data-ttu-id="64a29-103">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="64a29-103">IMAPIMessageSite : IUnknown</span></span>

  
  
<span data-ttu-id="64a29-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64a29-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64a29-105">操作消息，由表单查看器代码实现 (通常是响应此类) 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="64a29-105">Manipulates messages and is implemented by the form viewer code (typically a client application) that responds to such manipulation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="64a29-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="64a29-106">Header file:</span></span>  <br/> |<span data-ttu-id="64a29-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="64a29-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="64a29-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="64a29-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="64a29-109">邮件网站对象</span><span class="sxs-lookup"><span data-stu-id="64a29-109">Message site objects</span></span>  <br/> |
|<span data-ttu-id="64a29-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="64a29-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="64a29-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="64a29-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="64a29-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="64a29-112">Called by:</span></span>  <br/> |<span data-ttu-id="64a29-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="64a29-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="64a29-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="64a29-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="64a29-115">IID_IMAPIMessageSite</span><span class="sxs-lookup"><span data-stu-id="64a29-115">IID_IMAPIMessageSite</span></span>  <br/> |
|<span data-ttu-id="64a29-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="64a29-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="64a29-117">LPMAPIMESSAGESITE</span><span class="sxs-lookup"><span data-stu-id="64a29-117">LPMAPIMESSAGESITE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="64a29-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="64a29-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="64a29-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="64a29-119">GetSession</span></span>](imapimessagesite-getsession.md) <br/> |<span data-ttu-id="64a29-120">返回创建或打开当前邮件的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="64a29-120">Returns the MAPI session in which the current message was created or opened.</span></span>  <br/> |
|[<span data-ttu-id="64a29-121">GetStore</span><span class="sxs-lookup"><span data-stu-id="64a29-121">GetStore</span></span>](imapimessagesite-getstore.md) <br/> |<span data-ttu-id="64a29-122">返回包含当前邮件的邮件存储（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="64a29-122">Returns the message store that contains the current message, if such a store exists.</span></span>  <br/> |
|[<span data-ttu-id="64a29-123">GetFolder</span><span class="sxs-lookup"><span data-stu-id="64a29-123">GetFolder</span></span>](imapimessagesite-getfolder.md) <br/> |<span data-ttu-id="64a29-124">返回创建或打开当前邮件的文件夹（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="64a29-124">Returns the folder in which the current message was created or opened, if such a folder exists.</span></span>  <br/> |
|[<span data-ttu-id="64a29-125">GetMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-125">GetMessage</span></span>](imapimessagesite-getmessage.md) <br/> |<span data-ttu-id="64a29-126">返回当前邮件。</span><span class="sxs-lookup"><span data-stu-id="64a29-126">Returns the current message.</span></span>  <br/> |
|[<span data-ttu-id="64a29-127">GetFormManager</span><span class="sxs-lookup"><span data-stu-id="64a29-127">GetFormManager</span></span>](imapimessagesite-getformmanager.md) <br/> |<span data-ttu-id="64a29-128">返回一个表单管理器接口，表单服务器可以使用该界面打开另一台表单服务器。</span><span class="sxs-lookup"><span data-stu-id="64a29-128">Returns a form manager interface, which a form server can use to open another form server.</span></span>  <br/> |
|[<span data-ttu-id="64a29-129">NewMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-129">NewMessage</span></span>](imapimessagesite-newmessage.md) <br/> |<span data-ttu-id="64a29-130">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="64a29-130">Creates a new message.</span></span>  <br/> |
|[<span data-ttu-id="64a29-131">CopyMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-131">CopyMessage</span></span>](imapimessagesite-copymessage.md) <br/> |<span data-ttu-id="64a29-132">将当前邮件复制到文件夹。</span><span class="sxs-lookup"><span data-stu-id="64a29-132">Copies the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="64a29-133">MoveMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-133">MoveMessage</span></span>](imapimessagesite-movemessage.md) <br/> |<span data-ttu-id="64a29-134">将当前邮件移动到文件夹。</span><span class="sxs-lookup"><span data-stu-id="64a29-134">Moves the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="64a29-135">DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-135">DeleteMessage</span></span>](imapimessagesite-deletemessage.md) <br/> |<span data-ttu-id="64a29-136">删除当前邮件。</span><span class="sxs-lookup"><span data-stu-id="64a29-136">Deletes the current message.</span></span>  <br/> |
|[<span data-ttu-id="64a29-137">SaveMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-137">SaveMessage</span></span>](imapimessagesite-savemessage.md) <br/> |<span data-ttu-id="64a29-138">请求保存当前邮件。</span><span class="sxs-lookup"><span data-stu-id="64a29-138">Requests that the current message be saved.</span></span>  <br/> |
|[<span data-ttu-id="64a29-139">SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="64a29-139">SubmitMessage</span></span>](imapimessagesite-submitmessage.md) <br/> |<span data-ttu-id="64a29-140">请求将当前邮件排入队列进行传递。</span><span class="sxs-lookup"><span data-stu-id="64a29-140">Requests that the current message be queued for delivery.</span></span>  <br/> |
|[<span data-ttu-id="64a29-141">GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="64a29-141">GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md) <br/> |<span data-ttu-id="64a29-142">从邮件网站对象返回有关当前邮件的邮件网站功能的信息。</span><span class="sxs-lookup"><span data-stu-id="64a29-142">Returns information from a message site object about the message site's capabilities for the current message.</span></span>  <br/> |
|[<span data-ttu-id="64a29-143">GetLastError</span><span class="sxs-lookup"><span data-stu-id="64a29-143">GetLastError</span></span>](imapimessagesite-getlasterror.md) <br/> |<span data-ttu-id="64a29-144">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关邮件站点对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="64a29-144">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the message site object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="64a29-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64a29-145">See also</span></span>



[<span data-ttu-id="64a29-146">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="64a29-146">MAPI Interfaces</span></span>](mapi-interfaces.md)

