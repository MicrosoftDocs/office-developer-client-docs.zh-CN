---
title: PidTagMessageFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageFlags
api_type:
- HeaderDef
ms.assetid: 7561112b-ca72-4c49-a8a0-cc1879a4e151
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: f2e565dc8137edee441643a5d02a154f78737099
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777859"
---
# <a name="pidtagmessageflags-canonical-property"></a><span data-ttu-id="2263a-103">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="2263a-103">PidTagMessageFlags Canonical Property</span></span>

  
  
<span data-ttu-id="2263a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2263a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2263a-105">包含指示的原点和消息的当前状态标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2263a-105">Contains a bitmask of flags that indicate the origin and current state of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2263a-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="2263a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2263a-107">PR_MESSAGE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2263a-107">PR_MESSAGE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="2263a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2263a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2263a-109">0x0E07</span><span class="sxs-lookup"><span data-stu-id="2263a-109">0x0E07</span></span>  <br/> |
|<span data-ttu-id="2263a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2263a-110">Data type:</span></span>  <br/> |<span data-ttu-id="2263a-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2263a-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2263a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2263a-112">Area:</span></span>  <br/> |<span data-ttu-id="2263a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="2263a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2263a-114">备注</span><span class="sxs-lookup"><span data-stu-id="2263a-114">Remarks</span></span>

<span data-ttu-id="2263a-115">此属性是传输的同时发送和接收结束，具体取决于客户端应用程序或存储提供程序所涉及的不同值公开 nontransmittable message 属性。</span><span class="sxs-lookup"><span data-stu-id="2263a-115">This property is a nontransmittable message property exposed at both the sending and receiving ends of a transmission, with different values depending upon the client application or store provider involved.</span></span> <span data-ttu-id="2263a-116">此属性由客户端或消息存储提供程序创建和保存第一次，然后定期更新消息存储提供程序、 传输提供程序，和 MAPI 后台处理程序处理邮件消息时，其状态初始化更改。</span><span class="sxs-lookup"><span data-stu-id="2263a-116">This property is initialized by the client or message store provider when a message is created and saved for the first time and then updated periodically by the message store provider, a transport provider, and the MAPI spooler as the message is processed and its state changes.</span></span> 
  
<span data-ttu-id="2263a-117">此属性存在一条消息，before 和 after 提交，和上收到的邮件的所有副本。</span><span class="sxs-lookup"><span data-stu-id="2263a-117">This property exists on a message both before and after submission, and on all copies of the received message.</span></span> <span data-ttu-id="2263a-118">尽管不收件人属性，它向已公开不同根据是否已读取或修改的收件人的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="2263a-118">Although it is not a recipient property, it is exposed differently to each recipient according to whether it has been read or modified by that recipient.</span></span> 
  
<span data-ttu-id="2263a-119">此属性，可以设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="2263a-119">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="2263a-120">MSGFLAG_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="2263a-120">MSGFLAG_ASSOCIATED</span></span> 
  
> <span data-ttu-id="2263a-121">邮件是文件夹的关联的邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-121">The message is an associated message of a folder.</span></span> <span data-ttu-id="2263a-122">在客户端或提供程序具有到此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-122">The client or provider has read-only access to this flag.</span></span> <span data-ttu-id="2263a-123">关联的消息，不保留读/未读状态的情况下，将忽略 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-123">The MSGFLAG_READ flag is ignored for associated messages, which do not retain a read/unread state.</span></span> 
    
<span data-ttu-id="2263a-124">MSGFLAG_FROMME</span><span class="sxs-lookup"><span data-stu-id="2263a-124">MSGFLAG_FROMME</span></span> 
  
> <span data-ttu-id="2263a-125">消息的用户发送已接收邮件的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="2263a-125">The messaging user sending was the messaging user receiving the message.</span></span> <span data-ttu-id="2263a-126">在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。</span><span class="sxs-lookup"><span data-stu-id="2263a-126">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="2263a-127">此标志是为了由传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="2263a-127">This flag is meant to be set by the transport provider.</span></span> 
    
<span data-ttu-id="2263a-128">MSGFLAG_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="2263a-128">MSGFLAG_HASATTACH</span></span> 
  
> <span data-ttu-id="2263a-129">邮件已至少一个附件。</span><span class="sxs-lookup"><span data-stu-id="2263a-129">The message has at least one attachment.</span></span> <span data-ttu-id="2263a-130">此标志对应于消息的**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2263a-130">This flag corresponds to the message's **PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) property.</span></span> <span data-ttu-id="2263a-131">客户端具有只读访问权限此标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-131">The client has read-only access to this flag.</span></span> 
    
<span data-ttu-id="2263a-132">MSGFLAG_NRN_PENDING</span><span class="sxs-lookup"><span data-stu-id="2263a-132">MSGFLAG_NRN_PENDING</span></span> 
  
> <span data-ttu-id="2263a-133">Nonread 的报告需要发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-133">A nonread report needs to be sent for the message.</span></span> <span data-ttu-id="2263a-134">在客户端或提供程序具有到此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-134">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="2263a-135">MSGFLAG_ORIGIN_INTERNET</span><span class="sxs-lookup"><span data-stu-id="2263a-135">MSGFLAG_ORIGIN_INTERNET</span></span> 
  
> <span data-ttu-id="2263a-136">传入消息到达通过 Internet。</span><span class="sxs-lookup"><span data-stu-id="2263a-136">The incoming message arrived over the Internet.</span></span> <span data-ttu-id="2263a-137">它是组织外部，也可以从受信任的源无法考虑网关。</span><span class="sxs-lookup"><span data-stu-id="2263a-137">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="2263a-138">客户端应向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-138">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="2263a-139">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-139">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="2263a-140">MSGFLAG_ORIGIN_MISC_EXT</span><span class="sxs-lookup"><span data-stu-id="2263a-140">MSGFLAG_ORIGIN_MISC_EXT</span></span> 
  
> <span data-ttu-id="2263a-141">传入消息到达通过 X.400 或 Internet 外部链接。</span><span class="sxs-lookup"><span data-stu-id="2263a-141">The incoming message arrived over an external link other than X.400 or the Internet.</span></span> <span data-ttu-id="2263a-142">它是组织外部，也可以从受信任的源无法考虑网关。</span><span class="sxs-lookup"><span data-stu-id="2263a-142">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="2263a-143">客户端应向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-143">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="2263a-144">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-144">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="2263a-145">MSGFLAG_ORIGIN_X400</span><span class="sxs-lookup"><span data-stu-id="2263a-145">MSGFLAG_ORIGIN_X400</span></span> 
  
> <span data-ttu-id="2263a-146">传入消息到达通过 X.400 链接。</span><span class="sxs-lookup"><span data-stu-id="2263a-146">The incoming message arrived over an X.400 link.</span></span> <span data-ttu-id="2263a-147">它是组织外部，也可以从受信任的源无法考虑网关。</span><span class="sxs-lookup"><span data-stu-id="2263a-147">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="2263a-148">客户端应向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-148">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="2263a-149">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-149">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="2263a-150">MSGFLAG_READ</span><span class="sxs-lookup"><span data-stu-id="2263a-150">MSGFLAG_READ</span></span> 
  
> <span data-ttu-id="2263a-151">邮件标记为已读。</span><span class="sxs-lookup"><span data-stu-id="2263a-151">The message is marked as having been read.</span></span> <span data-ttu-id="2263a-152">这可能会调用随时[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)的结果。</span><span class="sxs-lookup"><span data-stu-id="2263a-152">This can occur as the result of a call at any time to [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> <span data-ttu-id="2263a-153">客户端还可以通过之前邮件已保存第一次调用一条消息**IMAPIProp::SetProps**方法设置此标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-153">Clients can also set this flag by calling a message's **IMAPIProp::SetProps** method before the message has been saved for the first time.</span></span> <span data-ttu-id="2263a-154">如果设置了**MSGFLAG_ASSOCIATED**标志，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-154">This flag is ignored if the **MSGFLAG_ASSOCIATED** flag is set.</span></span> 
    
<span data-ttu-id="2263a-155">MSGFLAG_RESEND</span><span class="sxs-lookup"><span data-stu-id="2263a-155">MSGFLAG_RESEND</span></span> 
  
> <span data-ttu-id="2263a-156">邮件包含与原件报表的重新发送操作的请求。</span><span class="sxs-lookup"><span data-stu-id="2263a-156">The message includes a request for a resend operation with a nondelivery report.</span></span> <span data-ttu-id="2263a-157">在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。</span><span class="sxs-lookup"><span data-stu-id="2263a-157">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> 
    
<span data-ttu-id="2263a-158">MSGFLAG_RN_PENDING</span><span class="sxs-lookup"><span data-stu-id="2263a-158">MSGFLAG_RN_PENDING</span></span> 
  
> <span data-ttu-id="2263a-159">阅读的报告需要发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-159">A read report needs to be sent for the message.</span></span> <span data-ttu-id="2263a-160">在客户端或提供程序具有到此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-160">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="2263a-161">MSGFLAG_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="2263a-161">MSGFLAG_SUBMIT</span></span> 
  
> <span data-ttu-id="2263a-162">邮件标记为发送由于[IMessage::SubmitMessage](imessage-submitmessage.md)调用。</span><span class="sxs-lookup"><span data-stu-id="2263a-162">The message is marked for sending as a result of a call to [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> <span data-ttu-id="2263a-163">消息存储提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="2263a-163">Message store providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="2263a-164">MSGFLAG_UNMODIFIED</span><span class="sxs-lookup"><span data-stu-id="2263a-164">MSGFLAG_UNMODIFIED</span></span> 
  
> <span data-ttu-id="2263a-165">尚未保存; 第一次修改传出消息尚未修改传入邮件，因为它已送达。</span><span class="sxs-lookup"><span data-stu-id="2263a-165">The outgoing message has not been modified since the first time that it was saved; the incoming message has not been modified since it was delivered.</span></span> 
    
<span data-ttu-id="2263a-166">MSGFLAG_UNSENT</span><span class="sxs-lookup"><span data-stu-id="2263a-166">MSGFLAG_UNSENT</span></span> 
  
> <span data-ttu-id="2263a-167">仍正在撰写的邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-167">The message is still being composed.</span></span> <span data-ttu-id="2263a-168">它保存，但尚未发送。</span><span class="sxs-lookup"><span data-stu-id="2263a-168">It is saved, but has not been sent.</span></span> <span data-ttu-id="2263a-169">在客户端或提供程序具有读/写访问此标志直到首次[IMAPIProp::SaveChanges](imapiprop-savechanges.md)调用和只读此后。</span><span class="sxs-lookup"><span data-stu-id="2263a-169">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="2263a-170">如果客户端发送邮件时不设置此标志，消息存储提供程序时调用**IMessage::SubmitMessage**设置它。</span><span class="sxs-lookup"><span data-stu-id="2263a-170">If a client doesn't set this flag by the time the message is sent, the message store provider sets it when **IMessage::SubmitMessage** is called.</span></span> <span data-ttu-id="2263a-171">通常情况下，此标志为清除状态后发送邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-171">Typically, this flag is cleared after the message is sent.</span></span> 
    
<span data-ttu-id="2263a-172">通过调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法读取标志值，客户端或消息存储提供程序可以随时检查邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="2263a-172">A client or message store provider can check the current state of the message at any time by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method to read the flag values.</span></span> <span data-ttu-id="2263a-173">在客户端或提供程序也可以调用[IMAPIProp::SetProps](imapiprop-setprops.md)方法更改当前具有读/写访问任何标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-173">The client or provider can also call the [IMAPIProp::SetProps](imapiprop-setprops.md) method to change any flags that currently have read/write access.</span></span> 
  
<span data-ttu-id="2263a-174">有几个标志始终是只读的。</span><span class="sxs-lookup"><span data-stu-id="2263a-174">Several of the flags are always read-only.</span></span> <span data-ttu-id="2263a-175">一些读/写，直到为**IMAPIProp::SetProps**而言，第一次调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法和此后将变为只读。</span><span class="sxs-lookup"><span data-stu-id="2263a-175">Some are read/write until the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and thereafter become read-only as far as **IMAPIProp::SetProps** is concerned.</span></span> <span data-ttu-id="2263a-176">一种，MSGFLAG_READ，可在稍后更改通过[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)。</span><span class="sxs-lookup"><span data-stu-id="2263a-176">One of these, MSGFLAG_READ, can be changed later through [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> 
  
<span data-ttu-id="2263a-177">此属性的初始值通常 MSGFLAG_UNSENT 和 MSGFLAG_UNMODIFIED 以指示一条消息，尚未已发送或更改。</span><span class="sxs-lookup"><span data-stu-id="2263a-177">The initial values for this property are typically MSGFLAG_UNSENT and MSGFLAG_UNMODIFIED to indicate a message that has not yet been sent or changed.</span></span> <span data-ttu-id="2263a-178">第二次保存后一条消息，消息存储提供程序将清除 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-178">When a message is saved for the second time, the message store provider clears the MSGFLAG_UNMODIFIED flag.</span></span> <span data-ttu-id="2263a-179">消息存储提供程序可以设置一条消息保存时的其他值为 MSGFLAG_HASATTACH 标志，指示邮件包含一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="2263a-179">Another value that a message store provider can set when a message is saved is the MSGFLAG_HASATTACH flag, indicating that the message has one or more attachments.</span></span> <span data-ttu-id="2263a-180">此设置从计算**PR_HASATTACH**属性。</span><span class="sxs-lookup"><span data-stu-id="2263a-180">The **PR_HASATTACH** property is computed from this setting.</span></span> 
  
<span data-ttu-id="2263a-181">当客户端调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法来发送消息时，消息存储提供程序创建的 MAPI 后台处理程序的副本，并通过设置 MSGFLAG_SUBMIT 标志更新此属性。</span><span class="sxs-lookup"><span data-stu-id="2263a-181">When a client calls the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send the message, the message store provider makes a copy of it for the MAPI spooler and updates this property by setting the MSGFLAG_SUBMIT flag.</span></span> <span data-ttu-id="2263a-182">消息存储提供程序还设置 MSGFLAG_UNSENT，如果尚未设置。</span><span class="sxs-lookup"><span data-stu-id="2263a-182">The message store provider also sets MSGFLAG_UNSENT if it is not yet set.</span></span> <span data-ttu-id="2263a-183">MSGFLAG_SUBMIT 指示已调用**SubmitMessage** ，开始发送过程中，并且邮件现在是只读的客户端的。</span><span class="sxs-lookup"><span data-stu-id="2263a-183">MSGFLAG_SUBMIT indicates that **SubmitMessage** has been called, beginning the send process, and that the message is now read-only to the client.</span></span> <span data-ttu-id="2263a-184">MSGFLAG_UNSENT 指示 MAPI 后台处理程序处理邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-184">MSGFLAG_UNSENT indicates that the MAPI spooler is handling the message.</span></span> <span data-ttu-id="2263a-185">如果取消发送过程，则消息存储提供程序将重置此标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-185">If the send process is canceled, the message store provider resets this flag.</span></span> 
  
<span data-ttu-id="2263a-186">时为邮件传递到传输提供程序指定，传输提供程序设置 MSGFLAG_FROMME 标志，如果发件人邮件上已收到消息的服务器上的同一个帐户。</span><span class="sxs-lookup"><span data-stu-id="2263a-186">When the message is given to a transport provider for delivery, the transport provider sets the MSGFLAG_FROMME flag if the sender had the same account on the messaging server as the message was received on.</span></span> <span data-ttu-id="2263a-187">传输提供程序设置为当前登录用户发送的传入消息的 MSGFLAG_FROMME。</span><span class="sxs-lookup"><span data-stu-id="2263a-187">Transport providers set MSGFLAG_FROMME for an incoming message that was sent by the currently logged on user.</span></span> <span data-ttu-id="2263a-188">客户端可以使用此值以确定它更适合比发件人名称已发送邮件文件夹的内容表中显示收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="2263a-188">A client can use this value to determine that it is more appropriate to show recipient names in the contents table of the Sent Items folder than sender names.</span></span> <span data-ttu-id="2263a-189">此外应与收件人姓名，而不是发件人名称显示已在撰写过程中保存和尚未发送的消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-189">Messages that have been saved during the composition process and not yet sent should also be displayed with recipient names rather than sender names.</span></span> 
  
<span data-ttu-id="2263a-190">传入消息，消息存储提供程序清除 MSGFLAG_READ 标志以重置其只读的状态。</span><span class="sxs-lookup"><span data-stu-id="2263a-190">For an incoming message, a message store provider clears the MSGFLAG_READ flag to reset its read status.</span></span> <span data-ttu-id="2263a-191">客户端可以设置或清除 MSGFLAG_READ 标志时需要更改的只读的状态和控制通过调用消息的[IMessage::SetReadFlag](imessage-setreadflag.md)方法或其文件夹的[IMAPIFolder 发送读取和 nonread 报告：SetReadFlags](imapifolder-setreadflags.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2263a-191">A client can set or clear the MSGFLAG_READ flag when it is necessary to change the read status and control the sending of read and nonread reports, by calling either the message's [IMessage::SetReadFlag](imessage-setreadflag.md) method or its folder's [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method.</span></span> <span data-ttu-id="2263a-192">这些方法，实现它们的对象之外的主要区别是 folder 方法可以影响一个、 多个，或所有文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-192">The main difference between these methods, other than the object implementing them, is that the folder method can affect one, several, or all of the messages in the folder.</span></span> <span data-ttu-id="2263a-193">消息方法影响一条消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-193">The message method affects a single message.</span></span> 
  
<span data-ttu-id="2263a-194">客户端还应测试 MSGFLAG_ORIGIN_X400、 MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT flags 的传入消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-194">A client should also test an incoming message for the MSGFLAG_ORIGIN_X400, MSGFLAG_ORIGIN_INTERNET, and MSGFLAG_ORIGIN_MISC_EXT flags.</span></span> <span data-ttu-id="2263a-195">这些标志由入站的传输提供程序设置，指示该消息到达来自网关无法考虑受信任的源。</span><span class="sxs-lookup"><span data-stu-id="2263a-195">These flags are set by the inbound transport provider and indicate that the message arrived from a source that the gateway cannot consider trusted.</span></span> <span data-ttu-id="2263a-196">这意味着发送组织外的邮件或内部但从工作站到网关未知。</span><span class="sxs-lookup"><span data-stu-id="2263a-196">This means the message originated either outside the organization, or internally but from a workstation not known to the gateway.</span></span> <span data-ttu-id="2263a-197">在任何情况下，可能未确认的发件人标识，并且没有引入到组织的计算机病毒的风险。</span><span class="sxs-lookup"><span data-stu-id="2263a-197">In any case, the identity of the sender may not be confirmed, and there is a risk of introducing a computer virus into the organization.</span></span> <span data-ttu-id="2263a-198">客户端应向用户显示一条警告消息，并提供一个选项，但不打开删除邮件。</span><span class="sxs-lookup"><span data-stu-id="2263a-198">The client should display a warning message to the user and offer an option of deleting the message without opening it.</span></span> 
  
<span data-ttu-id="2263a-199">消息存储提供程序设置为传入邮件 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="2263a-199">Message store providers set the MSGFLAG_UNMODIFIED flag for incoming messages.</span></span> <span data-ttu-id="2263a-200">MSGFLAG_UNMODIFIED 指示传递以来尚未更改一条消息。</span><span class="sxs-lookup"><span data-stu-id="2263a-200">MSGFLAG_UNMODIFIED indicates that a message has not been changed since delivery.</span></span> <span data-ttu-id="2263a-201">消息存储提供程序设置后，客户端无法清除此值。</span><span class="sxs-lookup"><span data-stu-id="2263a-201">A client cannot clear this value after it has been set by a message store provider.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2263a-202">相关资源</span><span class="sxs-lookup"><span data-stu-id="2263a-202">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2263a-203">协议规范</span><span class="sxs-lookup"><span data-stu-id="2263a-203">Protocol specifications</span></span>

<span data-ttu-id="2263a-204">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2263a-204">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2263a-205">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="2263a-205">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2263a-206">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2263a-206">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2263a-207">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="2263a-207">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2263a-208">头文件</span><span class="sxs-lookup"><span data-stu-id="2263a-208">Header files</span></span>

<span data-ttu-id="2263a-209">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2263a-209">Mapidefs.h</span></span>
  
> <span data-ttu-id="2263a-210">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2263a-210">Provides data type definitions.</span></span>
    
<span data-ttu-id="2263a-211">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2263a-211">Mapitags.h</span></span>
  
> <span data-ttu-id="2263a-212">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2263a-212">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2263a-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2263a-213">See also</span></span>



[<span data-ttu-id="2263a-214">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="2263a-214">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)


[<span data-ttu-id="2263a-215">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2263a-215">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2263a-216">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2263a-216">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2263a-217">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2263a-217">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2263a-218">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2263a-218">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

