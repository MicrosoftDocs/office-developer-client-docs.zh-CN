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
# <a name="pidtagmessageflags-canonical-property"></a><span data-ttu-id="fffa8-103">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="fffa8-103">PidTagMessageFlags Canonical Property</span></span>

  
  
<span data-ttu-id="fffa8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fffa8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fffa8-105">包含指示邮件的来源和当前状态的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fffa8-105">Contains a bitmask of flags that indicate the origin and current state of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fffa8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fffa8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fffa8-107">PR_MESSAGE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fffa8-107">PR_MESSAGE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="fffa8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fffa8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fffa8-109">0x0E07</span><span class="sxs-lookup"><span data-stu-id="fffa8-109">0x0E07</span></span>  <br/> |
|<span data-ttu-id="fffa8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fffa8-110">Data type:</span></span>  <br/> |<span data-ttu-id="fffa8-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="fffa8-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="fffa8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fffa8-112">Area:</span></span>  <br/> |<span data-ttu-id="fffa8-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="fffa8-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fffa8-114">备注</span><span class="sxs-lookup"><span data-stu-id="fffa8-114">Remarks</span></span>

<span data-ttu-id="fffa8-115">此属性是在传输的发送和接收端公开的不可传输邮件属性，根据涉及的客户端应用程序或存储提供程序，其值也不同。</span><span class="sxs-lookup"><span data-stu-id="fffa8-115">This property is a nontransmittable message property exposed at both the sending and receiving ends of a transmission, with different values depending upon the client application or store provider involved.</span></span> <span data-ttu-id="fffa8-116">此属性由客户端或邮件存储提供程序在首次创建和保存邮件时初始化，然后由邮件存储提供程序、传输提供程序和 MAPI 后台处理程序在邮件处理和其状态更改时定期更新。</span><span class="sxs-lookup"><span data-stu-id="fffa8-116">This property is initialized by the client or message store provider when a message is created and saved for the first time and then updated periodically by the message store provider, a transport provider, and the MAPI spooler as the message is processed and its state changes.</span></span> 
  
<span data-ttu-id="fffa8-117">此属性存在于提交之前和之后的邮件上，以及接收的邮件的所有副本上。</span><span class="sxs-lookup"><span data-stu-id="fffa8-117">This property exists on a message both before and after submission, and on all copies of the received message.</span></span> <span data-ttu-id="fffa8-118">虽然该属性不是收件人属性，但根据该收件人已读取或修改它，它向每个收件人公开的方式不同。</span><span class="sxs-lookup"><span data-stu-id="fffa8-118">Although it is not a recipient property, it is exposed differently to each recipient according to whether it has been read or modified by that recipient.</span></span> 
  
<span data-ttu-id="fffa8-119">可以为此属性设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="fffa8-119">One or more of the following flags can be set for this property:</span></span>
  
<span data-ttu-id="fffa8-120">MSGFLAG_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="fffa8-120">MSGFLAG_ASSOCIATED</span></span> 
  
> <span data-ttu-id="fffa8-121">邮件是文件夹的关联邮件。</span><span class="sxs-lookup"><span data-stu-id="fffa8-121">The message is an associated message of a folder.</span></span> <span data-ttu-id="fffa8-122">客户端或提供程序对此标志具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-122">The client or provider has read-only access to this flag.</span></span> <span data-ttu-id="fffa8-123">对于MSGFLAG_READ邮件，忽略该标记，这些邮件不会保留读/未读状态。</span><span class="sxs-lookup"><span data-stu-id="fffa8-123">The MSGFLAG_READ flag is ignored for associated messages, which do not retain a read/unread state.</span></span> 
    
<span data-ttu-id="fffa8-124">MSGFLAG_FROMME</span><span class="sxs-lookup"><span data-stu-id="fffa8-124">MSGFLAG_FROMME</span></span> 
  
> <span data-ttu-id="fffa8-125">邮件发送用户是接收邮件的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="fffa8-125">The messaging user sending was the messaging user receiving the message.</span></span> <span data-ttu-id="fffa8-126">客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。</span><span class="sxs-lookup"><span data-stu-id="fffa8-126">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="fffa8-127">此标志由传输提供程序设置。</span><span class="sxs-lookup"><span data-stu-id="fffa8-127">This flag is meant to be set by the transport provider.</span></span> 
    
<span data-ttu-id="fffa8-128">MSGFLAG_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="fffa8-128">MSGFLAG_HASATTACH</span></span> 
  
> <span data-ttu-id="fffa8-129">邮件至少具有一个附件。</span><span class="sxs-lookup"><span data-stu-id="fffa8-129">The message has at least one attachment.</span></span> <span data-ttu-id="fffa8-130">此标志对应于[PidTagHasAttachments](pidtaghasattachments-canonical-property.md) PR_HASATTACH (的邮件) 属性。 </span><span class="sxs-lookup"><span data-stu-id="fffa8-130">This flag corresponds to the message's **PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md)) property.</span></span> <span data-ttu-id="fffa8-131">客户端对此标志具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-131">The client has read-only access to this flag.</span></span> 
    
<span data-ttu-id="fffa8-132">MSGFLAG_NRN_PENDING</span><span class="sxs-lookup"><span data-stu-id="fffa8-132">MSGFLAG_NRN_PENDING</span></span> 
  
> <span data-ttu-id="fffa8-133">需要为邮件发送未读报告。</span><span class="sxs-lookup"><span data-stu-id="fffa8-133">A nonread report needs to be sent for the message.</span></span> <span data-ttu-id="fffa8-134">客户端或提供程序对此标志具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-134">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="fffa8-135">MSGFLAG_ORIGIN_INTERNET</span><span class="sxs-lookup"><span data-stu-id="fffa8-135">MSGFLAG_ORIGIN_INTERNET</span></span> 
  
> <span data-ttu-id="fffa8-136">传入的邮件通过 Internet 到达。</span><span class="sxs-lookup"><span data-stu-id="fffa8-136">The incoming message arrived over the Internet.</span></span> <span data-ttu-id="fffa8-137">它源自组织外部或网关无法认为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="fffa8-137">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="fffa8-138">客户端应该向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="fffa8-138">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="fffa8-139">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-139">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="fffa8-140">MSGFLAG_ORIGIN_MISC_EXT</span><span class="sxs-lookup"><span data-stu-id="fffa8-140">MSGFLAG_ORIGIN_MISC_EXT</span></span> 
  
> <span data-ttu-id="fffa8-141">传入邮件通过 X.400 或 Internet 外部链接到达。</span><span class="sxs-lookup"><span data-stu-id="fffa8-141">The incoming message arrived over an external link other than X.400 or the Internet.</span></span> <span data-ttu-id="fffa8-142">它源自组织外部或网关无法认为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="fffa8-142">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="fffa8-143">客户端应该向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="fffa8-143">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="fffa8-144">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-144">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="fffa8-145">MSGFLAG_ORIGIN_X400</span><span class="sxs-lookup"><span data-stu-id="fffa8-145">MSGFLAG_ORIGIN_X400</span></span> 
  
> <span data-ttu-id="fffa8-146">传入的邮件通过 X.400 链接到达。</span><span class="sxs-lookup"><span data-stu-id="fffa8-146">The incoming message arrived over an X.400 link.</span></span> <span data-ttu-id="fffa8-147">它源自组织外部或网关无法认为受信任的源。</span><span class="sxs-lookup"><span data-stu-id="fffa8-147">It originated either outside the organization or from a source the gateway cannot consider trusted.</span></span> <span data-ttu-id="fffa8-148">客户端应该向用户显示相应的消息。</span><span class="sxs-lookup"><span data-stu-id="fffa8-148">The client should display an appropriate message to the user.</span></span> <span data-ttu-id="fffa8-149">传输提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-149">Transport providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="fffa8-150">MSGFLAG_READ</span><span class="sxs-lookup"><span data-stu-id="fffa8-150">MSGFLAG_READ</span></span> 
  
> <span data-ttu-id="fffa8-151">邮件标记为已读。</span><span class="sxs-lookup"><span data-stu-id="fffa8-151">The message is marked as having been read.</span></span> <span data-ttu-id="fffa8-152">This can occur as the result of a call at any time to [IMessage：：SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md).</span><span class="sxs-lookup"><span data-stu-id="fffa8-152">This can occur as the result of a call at any time to [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> <span data-ttu-id="fffa8-153">客户端还可以在首次保存邮件之前调用邮件的 **IMAPIProp：：SetProps** 方法来设置此标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-153">Clients can also set this flag by calling a message's **IMAPIProp::SetProps** method before the message has been saved for the first time.</span></span> <span data-ttu-id="fffa8-154">如果设置了此标志 **，MSGFLAG_ASSOCIATED** 此标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-154">This flag is ignored if the **MSGFLAG_ASSOCIATED** flag is set.</span></span> 
    
<span data-ttu-id="fffa8-155">MSGFLAG_RESEND</span><span class="sxs-lookup"><span data-stu-id="fffa8-155">MSGFLAG_RESEND</span></span> 
  
> <span data-ttu-id="fffa8-156">邮件包含对未送达报告的重新发送操作的请求。</span><span class="sxs-lookup"><span data-stu-id="fffa8-156">The message includes a request for a resend operation with a nondelivery report.</span></span> <span data-ttu-id="fffa8-157">客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。</span><span class="sxs-lookup"><span data-stu-id="fffa8-157">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> 
    
<span data-ttu-id="fffa8-158">MSGFLAG_RN_PENDING</span><span class="sxs-lookup"><span data-stu-id="fffa8-158">MSGFLAG_RN_PENDING</span></span> 
  
> <span data-ttu-id="fffa8-159">需要为邮件发送阅读报告。</span><span class="sxs-lookup"><span data-stu-id="fffa8-159">A read report needs to be sent for the message.</span></span> <span data-ttu-id="fffa8-160">客户端或提供程序对此标志具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-160">The client or provider has read-only access to this flag.</span></span> 
    
<span data-ttu-id="fffa8-161">MSGFLAG_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="fffa8-161">MSGFLAG_SUBMIT</span></span> 
  
> <span data-ttu-id="fffa8-162">由于调用 [IMessage：：SubmitMessage，邮件被标记为发送](imessage-submitmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="fffa8-162">The message is marked for sending as a result of a call to [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> <span data-ttu-id="fffa8-163">邮件存储提供程序设置此标志;客户端具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="fffa8-163">Message store providers set this flag; the client has read-only access.</span></span> 
    
<span data-ttu-id="fffa8-164">MSGFLAG_UNMODIFIED</span><span class="sxs-lookup"><span data-stu-id="fffa8-164">MSGFLAG_UNMODIFIED</span></span> 
  
> <span data-ttu-id="fffa8-165">传出邮件自第一次保存以来尚未修改;传入邮件自传递后尚未修改。</span><span class="sxs-lookup"><span data-stu-id="fffa8-165">The outgoing message has not been modified since the first time that it was saved; the incoming message has not been modified since it was delivered.</span></span> 
    
<span data-ttu-id="fffa8-166">MSGFLAG_UNSENT</span><span class="sxs-lookup"><span data-stu-id="fffa8-166">MSGFLAG_UNSENT</span></span> 
  
> <span data-ttu-id="fffa8-167">邮件仍在撰写中。</span><span class="sxs-lookup"><span data-stu-id="fffa8-167">The message is still being composed.</span></span> <span data-ttu-id="fffa8-168">已保存，但尚未发送。</span><span class="sxs-lookup"><span data-stu-id="fffa8-168">It is saved, but has not been sent.</span></span> <span data-ttu-id="fffa8-169">客户端或提供程序对此标志具有读/写访问权限，直到第一次 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 调用和只读之后。</span><span class="sxs-lookup"><span data-stu-id="fffa8-169">The client or provider has read/write access to this flag until the first [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call and read-only thereafter.</span></span> <span data-ttu-id="fffa8-170">如果客户端在邮件发送时未设置此标志，邮件存储提供程序将在 **调用 IMessage：：SubmitMessage** 时设置它。</span><span class="sxs-lookup"><span data-stu-id="fffa8-170">If a client doesn't set this flag by the time the message is sent, the message store provider sets it when **IMessage::SubmitMessage** is called.</span></span> <span data-ttu-id="fffa8-171">通常，此标志在邮件发送后清除。</span><span class="sxs-lookup"><span data-stu-id="fffa8-171">Typically, this flag is cleared after the message is sent.</span></span> 
    
<span data-ttu-id="fffa8-172">客户端或邮件存储提供程序可以通过调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来读取标志值，随时检查邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="fffa8-172">A client or message store provider can check the current state of the message at any time by calling the [IMAPIProp::GetProps](imapiprop-getprops.md) method to read the flag values.</span></span> <span data-ttu-id="fffa8-173">客户端或提供程序还可以调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来更改当前具有读/写访问权限的任何标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-173">The client or provider can also call the [IMAPIProp::SetProps](imapiprop-setprops.md) method to change any flags that currently have read/write access.</span></span> 
  
<span data-ttu-id="fffa8-174">其中几个标志始终为只读。</span><span class="sxs-lookup"><span data-stu-id="fffa8-174">Several of the flags are always read-only.</span></span> <span data-ttu-id="fffa8-175">一些文件是可读写的，直到第一次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法，之后就 **IMAPIProp：：SetProps** 而言变为只读。</span><span class="sxs-lookup"><span data-stu-id="fffa8-175">Some are read/write until the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and thereafter become read-only as far as **IMAPIProp::SetProps** is concerned.</span></span> <span data-ttu-id="fffa8-176">稍后可通过 [IMessage：：SetReadFlag](imessage-setreadflag.md) 或 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md)更改其中一个MSGFLAG_READ，即 "IMessage：：SetReadFlags"。</span><span class="sxs-lookup"><span data-stu-id="fffa8-176">One of these, MSGFLAG_READ, can be changed later through [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md).</span></span> 
  
<span data-ttu-id="fffa8-177">此属性的初始值通常MSGFLAG_UNSENT MSGFLAG_UNMODIFIED，以指示尚未发送或已更改的邮件。</span><span class="sxs-lookup"><span data-stu-id="fffa8-177">The initial values for this property are typically MSGFLAG_UNSENT and MSGFLAG_UNMODIFIED to indicate a message that has not yet been sent or changed.</span></span> <span data-ttu-id="fffa8-178">当邮件第二次保存时，邮件存储提供程序会清除MSGFLAG_UNMODIFIED标记。</span><span class="sxs-lookup"><span data-stu-id="fffa8-178">When a message is saved for the second time, the message store provider clears the MSGFLAG_UNMODIFIED flag.</span></span> <span data-ttu-id="fffa8-179">邮件存储提供程序在保存邮件时可以设置的另一个值是 MSGFLAG_HASATTACH 标志，指示邮件具有一个或多个附件。</span><span class="sxs-lookup"><span data-stu-id="fffa8-179">Another value that a message store provider can set when a message is saved is the MSGFLAG_HASATTACH flag, indicating that the message has one or more attachments.</span></span> <span data-ttu-id="fffa8-180">the **PR_HASATTACH** property is computed from this setting.</span><span class="sxs-lookup"><span data-stu-id="fffa8-180">The **PR_HASATTACH** property is computed from this setting.</span></span> 
  
<span data-ttu-id="fffa8-181">当客户端调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法发送邮件时，邮件存储提供程序会为 MAPI 后台处理程序创建一个副本，然后通过设置 MSGFLAG_SUBMIT 标志来更新此属性。</span><span class="sxs-lookup"><span data-stu-id="fffa8-181">When a client calls the [IMessage::SubmitMessage](imessage-submitmessage.md) method to send the message, the message store provider makes a copy of it for the MAPI spooler and updates this property by setting the MSGFLAG_SUBMIT flag.</span></span> <span data-ttu-id="fffa8-182">如果尚未设置，邮件MSGFLAG_UNSENT提供程序还会设置邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="fffa8-182">The message store provider also sets MSGFLAG_UNSENT if it is not yet set.</span></span> <span data-ttu-id="fffa8-183">MSGFLAG_SUBMIT表示已调用 **SubmitMessage，** 开始发送过程，并且消息现在对客户端为只读。</span><span class="sxs-lookup"><span data-stu-id="fffa8-183">MSGFLAG_SUBMIT indicates that **SubmitMessage** has been called, beginning the send process, and that the message is now read-only to the client.</span></span> <span data-ttu-id="fffa8-184">MSGFLAG_UNSENT MAPI 后台处理程序正在处理消息。</span><span class="sxs-lookup"><span data-stu-id="fffa8-184">MSGFLAG_UNSENT indicates that the MAPI spooler is handling the message.</span></span> <span data-ttu-id="fffa8-185">如果发送过程被取消，邮件存储提供程序将重置此标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-185">If the send process is canceled, the message store provider resets this flag.</span></span> 
  
<span data-ttu-id="fffa8-186">将邮件给定给传输提供程序进行传递时，如果发件人在邮件传送服务器上具有与接收邮件相同的帐户，则传输提供程序将设置 MSGFLAG_FROMME 标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-186">When the message is given to a transport provider for delivery, the transport provider sets the MSGFLAG_FROMME flag if the sender had the same account on the messaging server as the message was received on.</span></span> <span data-ttu-id="fffa8-187">传输提供程序MSGFLAG_FROMME当前登录用户发送的传入邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="fffa8-187">Transport providers set MSGFLAG_FROMME for an incoming message that was sent by the currently logged on user.</span></span> <span data-ttu-id="fffa8-188">客户端可以使用此值来确定在"已发送邮件"文件夹的内容表中显示收件人姓名比显示发件人姓名更合适。</span><span class="sxs-lookup"><span data-stu-id="fffa8-188">A client can use this value to determine that it is more appropriate to show recipient names in the contents table of the Sent Items folder than sender names.</span></span> <span data-ttu-id="fffa8-189">在合成过程中保存但尚未发送的邮件也应使用收件人姓名而不是发件人姓名显示。</span><span class="sxs-lookup"><span data-stu-id="fffa8-189">Messages that have been saved during the composition process and not yet sent should also be displayed with recipient names rather than sender names.</span></span> 
  
<span data-ttu-id="fffa8-190">对于传入的邮件，邮件存储提供程序会清除 MSGFLAG_READ 标记以重置其读取状态。</span><span class="sxs-lookup"><span data-stu-id="fffa8-190">For an incoming message, a message store provider clears the MSGFLAG_READ flag to reset its read status.</span></span> <span data-ttu-id="fffa8-191">客户端可以通过调用邮件的 [IMessage：：SetReadFlag](imessage-setreadflag.md) 方法或文件夹的 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md) 方法，在必要时设置或清除 MSGFLAG_READ 标志，并控制读取和非读取报表的发送。</span><span class="sxs-lookup"><span data-stu-id="fffa8-191">A client can set or clear the MSGFLAG_READ flag when it is necessary to change the read status and control the sending of read and nonread reports, by calling either the message's [IMessage::SetReadFlag](imessage-setreadflag.md) method or its folder's [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method.</span></span> <span data-ttu-id="fffa8-192">这些方法之间的主要区别是文件夹方法会影响文件夹中的一个邮件、多个邮件或所有邮件，而不是实现它们的对象。</span><span class="sxs-lookup"><span data-stu-id="fffa8-192">The main difference between these methods, other than the object implementing them, is that the folder method can affect one, several, or all of the messages in the folder.</span></span> <span data-ttu-id="fffa8-193">message 方法影响单个邮件。</span><span class="sxs-lookup"><span data-stu-id="fffa8-193">The message method affects a single message.</span></span> 
  
<span data-ttu-id="fffa8-194">客户端还应测试传入邮件的 MSGFLAG_ORIGIN_X400、MSGFLAG_ORIGIN_INTERNET 和 MSGFLAG_ORIGIN_MISC_EXT 标志。</span><span class="sxs-lookup"><span data-stu-id="fffa8-194">A client should also test an incoming message for the MSGFLAG_ORIGIN_X400, MSGFLAG_ORIGIN_INTERNET, and MSGFLAG_ORIGIN_MISC_EXT flags.</span></span> <span data-ttu-id="fffa8-195">这些标志由入站传输提供程序设置，并指示邮件从网关无法认为受信任的源到达。</span><span class="sxs-lookup"><span data-stu-id="fffa8-195">These flags are set by the inbound transport provider and indicate that the message arrived from a source that the gateway cannot consider trusted.</span></span> <span data-ttu-id="fffa8-196">这意味着邮件来自组织外部或内部，但来自网关不知道的工作站。</span><span class="sxs-lookup"><span data-stu-id="fffa8-196">This means the message originated either outside the organization, or internally but from a workstation not known to the gateway.</span></span> <span data-ttu-id="fffa8-197">在任何情况下，可能无法确认发件人的身份，并且存在向组织引入计算机病毒的风险。</span><span class="sxs-lookup"><span data-stu-id="fffa8-197">In any case, the identity of the sender may not be confirmed, and there is a risk of introducing a computer virus into the organization.</span></span> <span data-ttu-id="fffa8-198">客户端应该向用户显示一条警告消息，并提供在不打开邮件的情况下删除邮件的选项。</span><span class="sxs-lookup"><span data-stu-id="fffa8-198">The client should display a warning message to the user and offer an option of deleting the message without opening it.</span></span> 
  
<span data-ttu-id="fffa8-199">邮件存储提供程序设置MSGFLAG_UNMODIFIED邮件的"邮件"标记。</span><span class="sxs-lookup"><span data-stu-id="fffa8-199">Message store providers set the MSGFLAG_UNMODIFIED flag for incoming messages.</span></span> <span data-ttu-id="fffa8-200">MSGFLAG_UNMODIFIED邮件表示邮件自传递后未发生更改。</span><span class="sxs-lookup"><span data-stu-id="fffa8-200">MSGFLAG_UNMODIFIED indicates that a message has not been changed since delivery.</span></span> <span data-ttu-id="fffa8-201">在邮件存储提供程序设置此值后，客户端无法清除此值。</span><span class="sxs-lookup"><span data-stu-id="fffa8-201">A client cannot clear this value after it has been set by a message store provider.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fffa8-202">相关资源</span><span class="sxs-lookup"><span data-stu-id="fffa8-202">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fffa8-203">协议规范</span><span class="sxs-lookup"><span data-stu-id="fffa8-203">Protocol specifications</span></span>

<span data-ttu-id="fffa8-204">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fffa8-204">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fffa8-205">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="fffa8-205">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fffa8-206">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fffa8-206">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fffa8-207">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="fffa8-207">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fffa8-208">头文件</span><span class="sxs-lookup"><span data-stu-id="fffa8-208">Header files</span></span>

<span data-ttu-id="fffa8-209">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fffa8-209">Mapidefs.h</span></span>
  
> <span data-ttu-id="fffa8-210">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fffa8-210">Provides data type definitions.</span></span>
    
<span data-ttu-id="fffa8-211">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fffa8-211">Mapitags.h</span></span>
  
> <span data-ttu-id="fffa8-212">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fffa8-212">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fffa8-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fffa8-213">See also</span></span>



[<span data-ttu-id="fffa8-214">IMsgStore::AbortSubmit</span><span class="sxs-lookup"><span data-stu-id="fffa8-214">IMsgStore::AbortSubmit</span></span>](imsgstore-abortsubmit.md)


[<span data-ttu-id="fffa8-215">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fffa8-215">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fffa8-216">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fffa8-216">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fffa8-217">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fffa8-217">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fffa8-218">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fffa8-218">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

