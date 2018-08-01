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
ms.openlocfilehash: 75ef8d6f2134e0269745f92dab1f790228692853
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775484"
---
# <a name="imapimessagesite--iunknown"></a><span data-ttu-id="f5d24-103">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f5d24-103">IMAPIMessageSite : IUnknown</span></span>

  
  
<span data-ttu-id="f5d24-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f5d24-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f5d24-105">处理邮件，并通过这种操作响应表单查看器代码 （通常客户端应用程序） 实现。</span><span class="sxs-lookup"><span data-stu-id="f5d24-105">Manipulates messages and is implemented by the form viewer code (typically a client application) that responds to such manipulation.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f5d24-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f5d24-106">Header file:</span></span>  <br/> |<span data-ttu-id="f5d24-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="f5d24-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="f5d24-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="f5d24-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="f5d24-109">消息网站对象</span><span class="sxs-lookup"><span data-stu-id="f5d24-109">Message site objects</span></span>  <br/> |
|<span data-ttu-id="f5d24-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="f5d24-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="f5d24-111">表单查看器</span><span class="sxs-lookup"><span data-stu-id="f5d24-111">Form viewers</span></span>  <br/> |
|<span data-ttu-id="f5d24-112">调用：</span><span class="sxs-lookup"><span data-stu-id="f5d24-112">Called by:</span></span>  <br/> |<span data-ttu-id="f5d24-113">窗体对象</span><span class="sxs-lookup"><span data-stu-id="f5d24-113">Form objects</span></span>  <br/> |
|<span data-ttu-id="f5d24-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="f5d24-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="f5d24-115">IID_IMAPIMessageSite</span><span class="sxs-lookup"><span data-stu-id="f5d24-115">IID_IMAPIMessageSite</span></span>  <br/> |
|<span data-ttu-id="f5d24-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="f5d24-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="f5d24-117">LPMAPIMESSAGESITE</span><span class="sxs-lookup"><span data-stu-id="f5d24-117">LPMAPIMESSAGESITE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="f5d24-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="f5d24-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="f5d24-119">GetSession</span><span class="sxs-lookup"><span data-stu-id="f5d24-119">GetSession</span></span>](imapimessagesite-getsession.md) <br/> |<span data-ttu-id="f5d24-120">返回当前消息是创建或打开的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="f5d24-120">Returns the MAPI session in which the current message was created or opened.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-121">GetStore</span><span class="sxs-lookup"><span data-stu-id="f5d24-121">GetStore</span></span>](imapimessagesite-getstore.md) <br/> |<span data-ttu-id="f5d24-122">如果存在此类存储，返回包含当前邮件的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="f5d24-122">Returns the message store that contains the current message, if such a store exists.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-123">GetFolder</span><span class="sxs-lookup"><span data-stu-id="f5d24-123">GetFolder</span></span>](imapimessagesite-getfolder.md) <br/> |<span data-ttu-id="f5d24-124">如果存在此类的文件夹，则返回已创建或打开，当前邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="f5d24-124">Returns the folder in which the current message was created or opened, if such a folder exists.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-125">GetMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-125">GetMessage</span></span>](imapimessagesite-getmessage.md) <br/> |<span data-ttu-id="f5d24-126">返回当前邮件。</span><span class="sxs-lookup"><span data-stu-id="f5d24-126">Returns the current message.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-127">GetFormManager</span><span class="sxs-lookup"><span data-stu-id="f5d24-127">GetFormManager</span></span>](imapimessagesite-getformmanager.md) <br/> |<span data-ttu-id="f5d24-128">返回一个窗体管理器接口，窗体服务器可用于打开窗体的另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="f5d24-128">Returns a form manager interface, which a form server can use to open another form server.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-129">NewMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-129">NewMessage</span></span>](imapimessagesite-newmessage.md) <br/> |<span data-ttu-id="f5d24-130">创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="f5d24-130">Creates a new message.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-131">CopyMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-131">CopyMessage</span></span>](imapimessagesite-copymessage.md) <br/> |<span data-ttu-id="f5d24-132">将当前的邮件复制到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="f5d24-132">Copies the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-133">MoveMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-133">MoveMessage</span></span>](imapimessagesite-movemessage.md) <br/> |<span data-ttu-id="f5d24-134">将当前邮件移动到文件夹中。</span><span class="sxs-lookup"><span data-stu-id="f5d24-134">Moves the current message to a folder.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-135">DeleteMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-135">DeleteMessage</span></span>](imapimessagesite-deletemessage.md) <br/> |<span data-ttu-id="f5d24-136">删除当前邮件。</span><span class="sxs-lookup"><span data-stu-id="f5d24-136">Deletes the current message.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-137">SaveMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-137">SaveMessage</span></span>](imapimessagesite-savemessage.md) <br/> |<span data-ttu-id="f5d24-138">保存当前消息的请求。</span><span class="sxs-lookup"><span data-stu-id="f5d24-138">Requests that the current message be saved.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-139">SubmitMessage</span><span class="sxs-lookup"><span data-stu-id="f5d24-139">SubmitMessage</span></span>](imapimessagesite-submitmessage.md) <br/> |<span data-ttu-id="f5d24-140">当前邮件在排队等待传送的请求。</span><span class="sxs-lookup"><span data-stu-id="f5d24-140">Requests that the current message be queued for delivery.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-141">GetSiteStatus</span><span class="sxs-lookup"><span data-stu-id="f5d24-141">GetSiteStatus</span></span>](imapimessagesite-getsitestatus.md) <br/> |<span data-ttu-id="f5d24-142">返回信息有关邮件消息网站对象中为当前消息的网站的功能。</span><span class="sxs-lookup"><span data-stu-id="f5d24-142">Returns information from a message site object about the message site's capabilities for the current message.</span></span>  <br/> |
|[<span data-ttu-id="f5d24-143">时出错</span><span class="sxs-lookup"><span data-stu-id="f5d24-143">GetLastError</span></span>](imapimessagesite-getlasterror.md) <br/> |<span data-ttu-id="f5d24-144">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误消息网站对象发生的信息。</span><span class="sxs-lookup"><span data-stu-id="f5d24-144">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the message site object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f5d24-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5d24-145">See also</span></span>



[<span data-ttu-id="f5d24-146">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="f5d24-146">MAPI Interfaces</span></span>](mapi-interfaces.md)

