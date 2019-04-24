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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321348"
---
# <a name="imapimessagesite--iunknown"></a><span data-ttu-id="b2579-103">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b2579-103">IMAPIMessageSite : IUnknown</span></span>

  
  
<span data-ttu-id="b2579-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b2579-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b2579-105">操作邮件并由响应此类操作的表单查看器代码 (通常是客户端应用程序) 实现。</span><span class="sxs-lookup"><span data-stu-id="b2579-105">Manipulates messages and is implemented by the form viewer code (typically a client application) that responds to such manipulation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b2579-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b2579-106">Header file:</span></span>  <br/> |<span data-ttu-id="b2579-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="b2579-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="b2579-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="b2579-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="b2579-109">邮件站点对象</span><span class="sxs-lookup"><span data-stu-id="b2579-109">Message site objects</span></span>  <br/> |
|<span data-ttu-id="b2579-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="b2579-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="b2579-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="b2579-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="b2579-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="b2579-112">Called by:</span></span>  <br/> |<span data-ttu-id="b2579-113">表单对象</span><span class="sxs-lookup"><span data-stu-id="b2579-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="b2579-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="b2579-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b2579-115">IID_IMAPIMessageSite</span><span class="sxs-lookup"><span data-stu-id="b2579-115">IID_IMAPIMessageSite</span></span>  <br/> |
|<span data-ttu-id="b2579-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="b2579-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="b2579-117">LPMAPIMESSAGESITE</span><span class="sxs-lookup"><span data-stu-id="b2579-117">LPMAPIMESSAGESITE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b2579-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="b2579-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="b2579-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="b2579-119">GetSession</span></span>](imapimessagesite-getsession.md) <br/> |<span data-ttu-id="b2579-120">返回在其中创建或打开当前邮件的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="b2579-120">Returns the MAPI session in which the current message was created or opened.</span></span>  <br/> |
|[<span data-ttu-id="b2579-121">GetStore</span><span class="sxs-lookup"><span data-stu-id="b2579-121">GetStore</span></span>](imapimessagesite-getstore.md) <br/> |<span data-ttu-id="b2579-122">如果存在这样的存储区, 则返回包含当前邮件的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="b2579-122">Returns the message store that contains the current message, if such a store exists.</span></span>  <br/> |
|[<span data-ttu-id="b2579-123">GetFolder</span><span class="sxs-lookup"><span data-stu-id="b2579-123">GetFolder</span></span>](imapimessagesite-getfolder.md) <br/> |<span data-ttu-id="b2579-124">返回在其中创建或打开当前邮件的文件夹 (如果存在这样的文件夹)。</span><span class="sxs-lookup"><span data-stu-id="b2579-124">Returns the folder in which the current message was created or opened, if such a folder exists.</span></span>  <br/> |
|[<span data-ttu-id="b2579-125">GetMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-125">GetMessage</span></span>](imapimessagesite-getmessage.md) <br/> |<span data-ttu-id="b2579-126">返回当前邮件。</span><span class="sxs-lookup"><span data-stu-id="b2579-126">Returns the current message.</span></span>  <br/> |
|[<span data-ttu-id="b2579-127">GetFormManager</span><span class="sxs-lookup"><span data-stu-id="b2579-127">GetFormManager</span></span>](imapimessagesite-getformmanager.md) <br/> |<span data-ttu-id="b2579-128">返回一个表单管理器接口, 表单服务器可以使用该接口打开另一个表单服务器。</span><span class="sxs-lookup"><span data-stu-id="b2579-128">Returns a form manager interface, which a form server can use to open another form server.</span></span>  <br/> |
|[<span data-ttu-id="b2579-129">NewMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-129">NewMessage</span></span>](imapimessagesite-newmessage.md) <br/> |<span data-ttu-id="b2579-130">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="b2579-130">Creates a new message.</span></span>  <br/> |
|[<span data-ttu-id="b2579-131">CopyMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-131">CopyMessage</span></span>](imapimessagesite-copymessage.md) <br/> |<span data-ttu-id="b2579-132">将当前邮件复制到一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b2579-132">Copies the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="b2579-133">MoveMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-133">MoveMessage</span></span>](imapimessagesite-movemessage.md) <br/> |<span data-ttu-id="b2579-134">将当前邮件移动到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b2579-134">Moves the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="b2579-135">DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-135">DeleteMessage</span></span>](imapimessagesite-deletemessage.md) <br/> |<span data-ttu-id="b2579-136">删除当前邮件。</span><span class="sxs-lookup"><span data-stu-id="b2579-136">Deletes the current message.</span></span>  <br/> |
|[<span data-ttu-id="b2579-137">SaveMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-137">SaveMessage</span></span>](imapimessagesite-savemessage.md) <br/> |<span data-ttu-id="b2579-138">请求保存当前邮件。</span><span class="sxs-lookup"><span data-stu-id="b2579-138">Requests that the current message be saved.</span></span>  <br/> |
|[<span data-ttu-id="b2579-139">SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="b2579-139">SubmitMessage</span></span>](imapimessagesite-submitmessage.md) <br/> |<span data-ttu-id="b2579-140">请求将当前邮件排队等待传递。</span><span class="sxs-lookup"><span data-stu-id="b2579-140">Requests that the current message be queued for delivery.</span></span>  <br/> |
|[<span data-ttu-id="b2579-141">GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="b2579-141">GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md) <br/> |<span data-ttu-id="b2579-142">从邮件网站对象返回有关当前邮件的邮件网站功能的信息。</span><span class="sxs-lookup"><span data-stu-id="b2579-142">Returns information from a message site object about the message site's capabilities for the current message.</span></span>  <br/> |
|[<span data-ttu-id="b2579-143">GetLastError</span><span class="sxs-lookup"><span data-stu-id="b2579-143">GetLastError</span></span>](imapimessagesite-getlasterror.md) <br/> |<span data-ttu-id="b2579-144">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关发生在邮件网站对象中的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b2579-144">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the message site object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b2579-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2579-145">See also</span></span>



[<span data-ttu-id="b2579-146">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b2579-146">MAPI Interfaces</span></span>](mapi-interfaces.md)

