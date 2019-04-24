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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5b660b592e77279a4d60f3a036724341352c9b6a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325739"
---
# <a name="pidtagmessageflags-canonical-property"></a><span data-ttu-id="56a63-103">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="56a63-103">PidTagMessageFlags Canonical Property</span></span>

  
  
<span data-ttu-id="56a63-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56a63-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56a63-105">包含指示邮件的源和当前状态的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="56a63-105">Contains a bitmask of flags that indicate the origin and current state of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56a63-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="56a63-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="56a63-107">PR_MESSAGE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="56a63-107">PR_MESSAGE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="56a63-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="56a63-108">Identifier:</span></span>  <br/> |<span data-ttu-id="56a63-109">0x0E07</span><span class="sxs-lookup"><span data-stu-id="56a63-109">0x0E07</span></span>  <br/> |
|<span data-ttu-id="56a63-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="56a63-110">Data type:</span></span>  <br/> |<span data-ttu-id="56a63-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="56a63-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="56a63-112">区域：</span><span class="sxs-lookup"><span data-stu-id="56a63-112">Area:</span></span>  <br/> |<span data-ttu-id="56a63-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="56a63-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="56a63-114">注解</span><span class="sxs-lookup"><span data-stu-id="56a63-114">Remarks</span></span>

<span data-ttu-id="56a63-115">此属性是在传输的发送端和接收端公开的 nontransmittable 消息属性, 具有不同的值, 具体取决于所涉及的客户端应用程序或存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="56a63-115">This property is a nontransmittable message property exposed at both the sending and receiving ends of a transmission, with different values depending upon the client application or store provider involved.</span></span> <span data-ttu-id="56a63-116">此属性由客户端或邮件存储提供程序在邮件首次创建和保存时进行初始化, 并在邮件存储提供程序、传输提供程序和 MAPI 后台处理程序定期更新, 同时处理邮件及其状态更新.</span><span class="sxs-lookup"><span data-stu-id="56a63-116">This property is initialized by the client or message store provider when a message is created and saved for the first time and then updated periodically by the message store provider, a transport provider, and the MAPI spooler as the message is processed and its state changes.</span></span> 
  
<span data-ttu-id="56a63-117">此属性在提交之前和之后都存在于邮件中, 并在收到的邮件的所有副本上。</span><span class="sxs-lookup"><span data-stu-id="56a63-117">This property exists on a message both before and after submission, and on all copies of the received message.</span></span> <span data-ttu-id="56a63-118">尽管它不是收件人属性, 但根据收件人是否已被该收件人阅读或修改, 它会以不同方式公开给每个收件人。</span><span class="sxs-lookup"><span data-stu-id="56a63-118">Although it is not a recipient property, it is exposed differently to each recipient according to whether it has been read or modified by that recipient.</span></span> 
  
<span data-ttu-id="56a63-119">可以为此属性设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="56a63-119">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="56a63-120">MSGFLAG_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="56a63-120">MSGFLAG_ASSOCIATED</span></span> 
  
> <span data-ttu-id="56a63-121">邮件是文件夹的关联邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-121">The message is an associated message of a folder.</span></span> <span data-ttu-id="56a63-122">客户端或提供程序具有此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-122">The client or provider has read-only access to this flag.</span></span> <span data-ttu-id="56a63-123">对于不保留已读/未读状态的关联邮件, 将忽略 MSGFLAG_READ 标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-123">The MSGFLAG_READ flag is ignored for associated messages, which do not retain a read/unread state.</span></span> 
    
<span data-ttu-id="56a63-124">MSGFLAG_FROMME</span><span class="sxs-lookup"><span data-stu-id="56a63-124">MSGFLAG_FROMME</span></span> 
  
> <span data-ttu-id="56a63-125">邮件传递用户发送是接收邮件的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="56a63-125">The messaging user sending was the messaging user receiving the message.</span></span> <span data-ttu-id="56a63-126">客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。</span><span class="sxs-lookup"><span data-stu-id="56a63-126">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="56a63-127">此标志应由传输提供程序进行设置。</span><span class="sxs-lookup"><span data-stu-id="56a63-127">This flag is meant to be set by the transport provider.</span></span> 
    
<span data-ttu-id="56a63-128">MSGFLAG_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="56a63-128">MSGFLAG_HASATTACH</span></span> 
  
> <span data-ttu-id="56a63-129">邮件至少有一个附件。</span><span class="sxs-lookup"><span data-stu-id="56a63-129">The message has at least one attachment.</span></span> <span data-ttu-id="56a63-130">此标志对应于邮件的**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="56a63-130">This flag corresponds to the message's **PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) property.</span></span> <span data-ttu-id="56a63-131">客户端对此标志具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-131">The client has read-only access to this flag.</span></span> 
    
<span data-ttu-id="56a63-132">MSGFLAG_NRN_PENDING</span><span class="sxs-lookup"><span data-stu-id="56a63-132">MSGFLAG_NRN_PENDING</span></span> 
  
> <span data-ttu-id="56a63-133">需要为邮件发送未读报告。</span><span class="sxs-lookup"><span data-stu-id="56a63-133">A nonread report needs to be sent for the message.</span></span> <span data-ttu-id="56a63-134">客户端或提供程序具有此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-134">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="56a63-135">MSGFLAG_ORIGIN_INTERNET</span><span class="sxs-lookup"><span data-stu-id="56a63-135">MSGFLAG_ORIGIN_INTERNET</span></span> 
  
> <span data-ttu-id="56a63-136">通过 Internet 到达的传入邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-136">The incoming message arrived over the Internet.</span></span> <span data-ttu-id="56a63-137">它来源于组织外部或网关无法视为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="56a63-137">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="56a63-138">客户端应向用户显示适当的消息。</span><span class="sxs-lookup"><span data-stu-id="56a63-138">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="56a63-139">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-139">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="56a63-140">MSGFLAG_ORIGIN_MISC_EXT</span><span class="sxs-lookup"><span data-stu-id="56a63-140">MSGFLAG_ORIGIN_MISC_EXT</span></span> 
  
> <span data-ttu-id="56a63-141">传入邮件通过除 X. 400 或 Internet 之外的外部链接到达。</span><span class="sxs-lookup"><span data-stu-id="56a63-141">The incoming message arrived over an external link other than X.400 or the Internet.</span></span> <span data-ttu-id="56a63-142">它来源于组织外部或网关无法视为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="56a63-142">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="56a63-143">客户端应向用户显示适当的消息。</span><span class="sxs-lookup"><span data-stu-id="56a63-143">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="56a63-144">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-144">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="56a63-145">MSGFLAG_ORIGIN_X400</span><span class="sxs-lookup"><span data-stu-id="56a63-145">MSGFLAG_ORIGIN_X400</span></span> 
  
> <span data-ttu-id="56a63-146">传入邮件通过 400. 400 链接到达。</span><span class="sxs-lookup"><span data-stu-id="56a63-146">The incoming message arrived over an X.400 link.</span></span> <span data-ttu-id="56a63-147">它来源于组织外部或网关无法视为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="56a63-147">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="56a63-148">客户端应向用户显示适当的消息。</span><span class="sxs-lookup"><span data-stu-id="56a63-148">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="56a63-149">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-149">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="56a63-150">MSGFLAG_READ</span><span class="sxs-lookup"><span data-stu-id="56a63-150">MSGFLAG_READ</span></span> 
  
> <span data-ttu-id="56a63-151">邮件被标记为已读。</span><span class="sxs-lookup"><span data-stu-id="56a63-151">The message is marked as having been read.</span></span> <span data-ttu-id="56a63-152">在任何时候调用[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)时, 都会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="56a63-152">This can occur as the result of a call at any time to [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> <span data-ttu-id="56a63-153">在首次保存邮件之前, 客户端还可以通过调用邮件的**IMAPIProp:: SetProps**方法来设置此标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-153">Clients can also set this flag by calling a message's **IMAPIProp::SetProps** method before the message has been saved for the first time.</span></span> <span data-ttu-id="56a63-154">如果设置了**MSGFLAG_ASSOCIATED**标志, 则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-154">This flag is ignored if the **MSGFLAG_ASSOCIATED** flag is set.</span></span> 
    
<span data-ttu-id="56a63-155">MSGFLAG_RESEND</span><span class="sxs-lookup"><span data-stu-id="56a63-155">MSGFLAG_RESEND</span></span> 
  
> <span data-ttu-id="56a63-156">该邮件包含一个使用 nondelivery 报告的重发操作请求。</span><span class="sxs-lookup"><span data-stu-id="56a63-156">The message includes a request for a resend operation with a nondelivery report.</span></span> <span data-ttu-id="56a63-157">客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。</span><span class="sxs-lookup"><span data-stu-id="56a63-157">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> 
    
<span data-ttu-id="56a63-158">MSGFLAG_RN_PENDING</span><span class="sxs-lookup"><span data-stu-id="56a63-158">MSGFLAG_RN_PENDING</span></span> 
  
> <span data-ttu-id="56a63-159">需要为邮件发送已读报告。</span><span class="sxs-lookup"><span data-stu-id="56a63-159">A read report needs to be sent for the message.</span></span> <span data-ttu-id="56a63-160">客户端或提供程序具有此标志的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-160">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="56a63-161">MSGFLAG_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="56a63-161">MSGFLAG_SUBMIT</span></span> 
  
> <span data-ttu-id="56a63-162">由于调用[IMessage:: SubmitMessage](imessage-submitmessage.md), 邮件被标记为要发送。</span><span class="sxs-lookup"><span data-stu-id="56a63-162">The message is marked for sending as a result of a call to [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> <span data-ttu-id="56a63-163">邮件存储提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="56a63-163">Message store providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="56a63-164">MSGFLAG_UNMODIFIED</span><span class="sxs-lookup"><span data-stu-id="56a63-164">MSGFLAG_UNMODIFIED</span></span> 
  
> <span data-ttu-id="56a63-165">传出邮件自第一次保存后未进行过修改;传入邮件自传递后未进行修改。</span><span class="sxs-lookup"><span data-stu-id="56a63-165">The outgoing message has not been modified since the first time that it was saved; the incoming message has not been modified since it was delivered.</span></span> 
    
<span data-ttu-id="56a63-166">MSGFLAG_UNSENT</span><span class="sxs-lookup"><span data-stu-id="56a63-166">MSGFLAG_UNSENT</span></span> 
  
> <span data-ttu-id="56a63-167">邮件仍在撰写中。</span><span class="sxs-lookup"><span data-stu-id="56a63-167">The message is still being composed.</span></span> <span data-ttu-id="56a63-168">它将被保存, 但尚未发送。</span><span class="sxs-lookup"><span data-stu-id="56a63-168">It is saved, but has not been sent.</span></span> <span data-ttu-id="56a63-169">客户端或提供程序对此标志具有读/写访问权限, 直到第一个[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)调用和此后为只读。</span><span class="sxs-lookup"><span data-stu-id="56a63-169">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="56a63-170">如果客户端在发送邮件时不设置此标记, 则邮件存储提供程序会在调用**IMessage:: SubmitMessage**时对其进行设置。</span><span class="sxs-lookup"><span data-stu-id="56a63-170">If a client doesn't set this flag by the time the message is sent, the message store provider sets it when **IMessage::SubmitMessage** is called.</span></span> <span data-ttu-id="56a63-171">通常情况下, 在发送邮件后清除此标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-171">Typically, this flag is cleared after the message is sent.</span></span> 
    
<span data-ttu-id="56a63-172">通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md)方法读取标志值, 客户端或邮件存储提供程序可以随时检查邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="56a63-172">A client or message store provider can check the current state of the message at any time by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method to read the flag values.</span></span> <span data-ttu-id="56a63-173">客户端或提供程序也可以调用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法来更改当前具有读/写访问权限的任何标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-173">The client or provider can also call the [IMAPIProp::SetProps](imapiprop-setprops.md) method to change any flags that currently have read/write access.</span></span> 
  
<span data-ttu-id="56a63-174">有些标志始终为只读。</span><span class="sxs-lookup"><span data-stu-id="56a63-174">Several of the flags are always read-only.</span></span> <span data-ttu-id="56a63-175">有些是可读写的, 直到第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法, 之后, 在**IMAPIProp:: SetProps**相关时将变为只读。</span><span class="sxs-lookup"><span data-stu-id="56a63-175">Some are read/write until the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and thereafter become read-only as far as **IMAPIProp::SetProps** is concerned.</span></span> <span data-ttu-id="56a63-176">可以在稍后通过[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)更改其中一个 MSGFLAG_READ。</span><span class="sxs-lookup"><span data-stu-id="56a63-176">One of these, MSGFLAG_READ, can be changed later through [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> 
  
<span data-ttu-id="56a63-177">此属性的初始值通常为 MSGFLAG_UNSENT 和 MSGFLAG_UNMODIFIED, 以指示尚未发送或更改的邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-177">The initial values for this property are typically MSGFLAG_UNSENT and MSGFLAG_UNMODIFIED to indicate a message that has not yet been sent or changed.</span></span> <span data-ttu-id="56a63-178">在第二次保存邮件时, 邮件存储提供程序将清除 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-178">When a message is saved for the second time, the message store provider clears the MSGFLAG_UNMODIFIED flag.</span></span> <span data-ttu-id="56a63-179">保存邮件时, 邮件存储提供程序可以设置的另一个值是 MSGFLAG_HASATTACH 标志, 指示邮件包含一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="56a63-179">Another value that a message store provider can set when a message is saved is the MSGFLAG_HASATTACH flag, indicating that the message has one or more attachments.</span></span> <span data-ttu-id="56a63-180">**PR_HASATTACH**属性是从此设置计算而来。</span><span class="sxs-lookup"><span data-stu-id="56a63-180">The **PR_HASATTACH** property is computed from this setting.</span></span> 
  
<span data-ttu-id="56a63-181">当客户端调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法发送邮件时, 邮件存储提供程序会为 MAPI 后台处理程序创建一个副本, 并通过设置 MSGFLAG_SUBMIT 标志来更新该属性。</span><span class="sxs-lookup"><span data-stu-id="56a63-181">When a client calls the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send the message, the message store provider makes a copy of it for the MAPI spooler and updates this property by setting the MSGFLAG_SUBMIT flag.</span></span> <span data-ttu-id="56a63-182">如果尚未设置, 邮件存储提供程序还会设置 MSGFLAG_UNSENT。</span><span class="sxs-lookup"><span data-stu-id="56a63-182">The message store provider also sets MSGFLAG_UNSENT if it is not yet set.</span></span> <span data-ttu-id="56a63-183">MSGFLAG_SUBMIT 指示已调用**SubmitMessage** , 即将开始发送过程, 并且该邮件目前对客户端是只读的。</span><span class="sxs-lookup"><span data-stu-id="56a63-183">MSGFLAG_SUBMIT indicates that **SubmitMessage** has been called, beginning the send process, and that the message is now read-only to the client.</span></span> <span data-ttu-id="56a63-184">MSGFLAG_UNSENT 指示 MAPI 后台处理程序正在处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-184">MSGFLAG_UNSENT indicates that the MAPI spooler is handling the message.</span></span> <span data-ttu-id="56a63-185">如果发送过程被取消, 邮件存储提供程序将重置此标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-185">If the send process is canceled, the message store provider resets this flag.</span></span> 
  
<span data-ttu-id="56a63-186">将邮件传递给传输提供程序进行传递时, 如果发件人在邮件服务器上具有相同的帐户, 则传输提供程序将设置 MSGFLAG_FROMME 标志 (如果在上接收邮件)。</span><span class="sxs-lookup"><span data-stu-id="56a63-186">When the message is given to a transport provider for delivery, the transport provider sets the MSGFLAG_FROMME flag if the sender had the same account on the messaging server as the message was received on.</span></span> <span data-ttu-id="56a63-187">传输提供程序为当前登录用户发送的传入邮件设置 MSGFLAG_FROMME。</span><span class="sxs-lookup"><span data-stu-id="56a63-187">Transport providers set MSGFLAG_FROMME for an incoming message that was sent by the currently logged on user.</span></span> <span data-ttu-id="56a63-188">客户端可以使用此值来确定更适合在 "已发送邮件" 文件夹的 "内容" 表中显示收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="56a63-188">A client can use this value to determine that it is more appropriate to show recipient names in the contents table of the Sent Items folder than sender names.</span></span> <span data-ttu-id="56a63-189">在撰写过程中保存但尚未发送的邮件也应显示收件人姓名而不是发件人姓名。</span><span class="sxs-lookup"><span data-stu-id="56a63-189">Messages that have been saved during the composition process and not yet sent should also be displayed with recipient names rather than sender names.</span></span> 
  
<span data-ttu-id="56a63-190">对于传入邮件, 邮件存储提供程序将清除 MSGFLAG_READ 标志以重置其读取状态。</span><span class="sxs-lookup"><span data-stu-id="56a63-190">For an incoming message, a message store provider clears the MSGFLAG_READ flag to reset its read status.</span></span> <span data-ttu-id="56a63-191">当需要更改读取状态并控制读取和未读报告的发送时, 客户端可以设置或清除 MSGFLAG_READ 标志, 方法是调用邮件的[IMessage:: SetReadFlag](imessage-setreadflag.md)方法或其文件夹的[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)方法。</span><span class="sxs-lookup"><span data-stu-id="56a63-191">A client can set or clear the MSGFLAG_READ flag when it is necessary to change the read status and control the sending of read and nonread reports, by calling either the message's [IMessage::SetReadFlag](imessage-setreadflag.md) method or its folder's [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method.</span></span> <span data-ttu-id="56a63-192">这些方法 (而不是实现它们的对象) 之间的主要区别是, folder 方法可以影响文件夹中的一个、多个或所有邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-192">The main difference between these methods, other than the object implementing them, is that the folder method can affect one, several, or all of the messages in the folder.</span></span> <span data-ttu-id="56a63-193">message 方法影响单个邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-193">The message method affects a single message.</span></span> 
  
<span data-ttu-id="56a63-194">客户端还应为 MSGFLAG_ORIGIN_X400、MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT 标志测试传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="56a63-194">A client should also test an incoming message for the MSGFLAG_ORIGIN_X400, MSGFLAG_ORIGIN_INTERNET, and MSGFLAG_ORIGIN_MISC_EXT flags.</span></span> <span data-ttu-id="56a63-195">这些标志由入站传输提供程序设置, 并指示邮件到达来自网关无法认为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="56a63-195">These flags are set by the inbound transport provider and indicate that the message arrived from a source that the gateway cannot consider trusted.</span></span> <span data-ttu-id="56a63-196">这意味着邮件在组织外部, 或在内部, 而不是由网关所知的工作站发起。</span><span class="sxs-lookup"><span data-stu-id="56a63-196">This means the message originated either outside the organization, or internally but from a workstation not known to the gateway.</span></span> <span data-ttu-id="56a63-197">在任何情况下, 可能不会确认发件人的身份, 并且存在将计算机病毒引入组织的风险。</span><span class="sxs-lookup"><span data-stu-id="56a63-197">In any case, the identity of the sender may not be confirmed, and there is a risk of introducing a computer virus into the organization.</span></span> <span data-ttu-id="56a63-198">客户端应向用户显示一条警告消息, 并提供在不打开邮件的情况下删除邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="56a63-198">The client should display a warning message to the user and offer an option of deleting the message without opening it.</span></span> 
  
<span data-ttu-id="56a63-199">邮件存储提供程序设置传入邮件的 MSGFLAG_UNMODIFIED 标志。</span><span class="sxs-lookup"><span data-stu-id="56a63-199">Message store providers set the MSGFLAG_UNMODIFIED flag for incoming messages.</span></span> <span data-ttu-id="56a63-200">MSGFLAG_UNMODIFIED 指示邮件自传递后未发生更改。</span><span class="sxs-lookup"><span data-stu-id="56a63-200">MSGFLAG_UNMODIFIED indicates that a message has not been changed since delivery.</span></span> <span data-ttu-id="56a63-201">客户端无法在邮件存储提供程序设置后清除此值。</span><span class="sxs-lookup"><span data-stu-id="56a63-201">A client cannot clear this value after it has been set by a message store provider.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="56a63-202">相关资源</span><span class="sxs-lookup"><span data-stu-id="56a63-202">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="56a63-203">协议规范</span><span class="sxs-lookup"><span data-stu-id="56a63-203">Protocol specifications</span></span>

<span data-ttu-id="56a63-204">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56a63-204">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56a63-205">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="56a63-205">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="56a63-206">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56a63-206">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56a63-207">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="56a63-207">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="56a63-208">头文件</span><span class="sxs-lookup"><span data-stu-id="56a63-208">Header files</span></span>

<span data-ttu-id="56a63-209">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="56a63-209">Mapidefs.h</span></span>
  
> <span data-ttu-id="56a63-210">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="56a63-210">Provides data type definitions.</span></span>
    
<span data-ttu-id="56a63-211">Mapitags</span><span class="sxs-lookup"><span data-stu-id="56a63-211">Mapitags.h</span></span>
  
> <span data-ttu-id="56a63-212">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="56a63-212">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56a63-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56a63-213">See also</span></span>



[<span data-ttu-id="56a63-214">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="56a63-214">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)


[<span data-ttu-id="56a63-215">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="56a63-215">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="56a63-216">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="56a63-216">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="56a63-217">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="56a63-217">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="56a63-218">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="56a63-218">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

