---
title: MAPI 收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 88a4360d-6ab8-466e-8ebd-af80227ee00a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ebdaf47b4f20763574ffac73bddeb3eb4eeb95df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423690"
---
# <a name="mapi-recipients"></a><span data-ttu-id="be79d-103">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="be79d-103">MAPI Recipients</span></span>

  
  
<span data-ttu-id="be79d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="be79d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="be79d-105">要传输的每封邮件都有一个或多个收件人，或者有一组描述邮件传递位置的属性。</span><span class="sxs-lookup"><span data-stu-id="be79d-105">Every message to be transmitted has one or more recipients, or a set of properties that describe where the message is to be delivered.</span></span> <span data-ttu-id="be79d-106">由于收件人仅在邮件上下文中使用，因此被视为邮件的子对象，而不是单独的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="be79d-106">Because recipients are used only in the context of a message, they are considered subobjects of a message instead of separate MAPI objects.</span></span> <span data-ttu-id="be79d-107">客户端和提供程序使用 **IMessage** 接口与收件人一起工作。</span><span class="sxs-lookup"><span data-stu-id="be79d-107">Clients and providers work with recipients using the **IMessage** interface.</span></span> <span data-ttu-id="be79d-108">有关详细信息，请参阅 [IMessage ： IMAPIProp](imessageimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-108">For more information, see [IMessage : IMAPIProp](imessageimapiprop.md).</span></span>
  
<span data-ttu-id="be79d-109">客户端通过其收件人表访问邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-109">Clients access a message's recipients through its recipient table.</span></span> <span data-ttu-id="be79d-110">每封邮件都有一个收件人表，其中包含有关其每个收件人的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="be79d-110">Every message has a recipient table that contains summary information about each of its recipients.</span></span> <span data-ttu-id="be79d-111">表中包含的列取决于邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="be79d-111">The columns included in the table depend on the state of the message.</span></span> <span data-ttu-id="be79d-112">当邮件在撰写下时，其收件人可能只有三列：</span><span class="sxs-lookup"><span data-stu-id="be79d-112">When a message is under composition, its recipients might have only three columns in the table:</span></span>
  
- <span data-ttu-id="be79d-113">显示名称，或 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="be79d-113">Display name, or **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="be79d-114">收件人 **类型，PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="be79d-114">Recipient type, or **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="be79d-115">行标识符或 **PR_ROWID (** [PidTagRowid](pidtagrowid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="be79d-115">Row identifier, or **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span></span>
    
<span data-ttu-id="be79d-116">邮件完成名称解析过程后，每个收件人也将具有条目标识符，PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。 </span><span class="sxs-lookup"><span data-stu-id="be79d-116">After the message has undergone the name resolution process, each recipient will also have an entry identifier, or **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column.</span></span> <span data-ttu-id="be79d-117">提交邮件后，收件人表中的行将再添加两列：</span><span class="sxs-lookup"><span data-stu-id="be79d-117">And when the message has been submitted, the rows in the recipient table will add two more columns:</span></span>
  
- <span data-ttu-id="be79d-118">地址类型，或 **PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="be79d-118">Address type, or **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="be79d-119">传输责任或 **PR_RESPONSIBILITY (** [PidTagResponsibility)](pidtagresponsibility-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="be79d-119">Transport responsibility, or **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span></span>
    
<span data-ttu-id="be79d-120">客户端可以通过调用邮件的 **IMessage：：GetRecipientTable** 方法或 **IMAPIProp：：OpenProperty** 方法检索邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="be79d-120">Clients can retrieve a message's recipient table by calling its **IMessage::GetRecipientTable** method or its **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="be79d-121">有关详细信息，请参阅 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-121">For more information, see [IMessage::GetRecipientTable](imessage-getrecipienttable.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="be79d-122">邮件存储提供程序应支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="be79d-122">Message store providers are expected to support both of these approaches.</span></span> <span data-ttu-id="be79d-123">**OpenProperty** 方法要求客户端将 IID_IMAPITable 指定为接口标识符，PR_MESSAGE_RECIPIENTS **属性标记**。</span><span class="sxs-lookup"><span data-stu-id="be79d-123">The **OpenProperty** approach requires that the client specify IID_IMAPITable as the interface identifier and **PR_MESSAGE_RECIPIENTS** as the property tag.</span></span> <span data-ttu-id="be79d-124">**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 是表示邮件的收件人表的 table 对象属性。</span><span class="sxs-lookup"><span data-stu-id="be79d-124">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) is a table object property that represents a message's recipient table.</span></span> <span data-ttu-id="be79d-125">邮件存储提供程序需要为PR_MESSAGE_RECIPIENTS设置值，并包括到 **从 IMAPIProp：：GetPropList** 方法返回的属性标记数组中。</span><span class="sxs-lookup"><span data-stu-id="be79d-125">Message store providers are required to set **PR_MESSAGE_RECIPIENTS** for each message and include it in the array of property tags returned from the **IMAPIProp::GetPropList** method.</span></span> <span data-ttu-id="be79d-126">有关详细信息，请参阅 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-126">For more information, see [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span>
  
<span data-ttu-id="be79d-127">有关如何使用收件人表的信息，请参阅 [收件人表](recipient-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-127">For more information about how to work with a recipient table, see [Recipient Tables](recipient-tables.md).</span></span>
  
<span data-ttu-id="be79d-128">除了用于访问收件人表之外，PR_MESSAGE_RECIPIENTS **可以使用：**</span><span class="sxs-lookup"><span data-stu-id="be79d-128">In addition to being used to access a recipient table, **PR_MESSAGE_RECIPIENTS** can be used:</span></span> 
  
- <span data-ttu-id="be79d-129">使用 **IMAPIProp：：CopyTo** 或 **IMAPIProp：：CopyProps** 在复制时排除或包括收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-129">With **IMAPIProp::CopyTo** or **IMAPIProp::CopyProps** to exclude or include recipients when copying.</span></span> <span data-ttu-id="be79d-130">有关详细信息，请参阅 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-130">For more information see, [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md).</span></span>
    
- <span data-ttu-id="be79d-131">在子对象限制中，指示子对象应应用于收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-131">In a subobject restriction to indicate that the child restiction should apply to recipients.</span></span>
    
<span data-ttu-id="be79d-132">客户端可以通过复制 MAPI 通讯簿中的条目或创建新条目将收件人添加到邮件。</span><span class="sxs-lookup"><span data-stu-id="be79d-132">Clients can add recipients to a message by copying entries from the MAPI address book or by creating new entries.</span></span> <span data-ttu-id="be79d-133">这些新条目称为一次使用，可以暂时存在或永久保存在可修改的容器中。</span><span class="sxs-lookup"><span data-stu-id="be79d-133">These new entries, called one-offs, can exist temporarily or be saved permanently in a modifiable container.</span></span> <span data-ttu-id="be79d-134">从通讯簿获取的收件人具有与其通讯簿提供程序关联的条目标识符，而一次收件人具有 MAPI 格式的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="be79d-134">Whereas recipients that are taken from the address book have entry identifiers associated with their address book provider, one-off recipients have entry identifiers that are formatted by MAPI.</span></span> <span data-ttu-id="be79d-135">传输提供程序和客户端将一次输入标识符与各种类型的地址关联。</span><span class="sxs-lookup"><span data-stu-id="be79d-135">Transport providers and clients associate one-off entry identifiers with various types of addresses.</span></span> 
  
<span data-ttu-id="be79d-136">传输提供程序调用 **IMAPISupport：：CreateOneOff** 为传出邮件上的地址创建一次条目标识符，当：</span><span class="sxs-lookup"><span data-stu-id="be79d-136">Transport providers call **IMAPISupport::CreateOneOff** to create a one-off entry identifier for an address on an outgoing message when:</span></span> 
  
- <span data-ttu-id="be79d-137">该地址属于网关。</span><span class="sxs-lookup"><span data-stu-id="be79d-137">The address belongs to a gateway.</span></span>
    
- <span data-ttu-id="be79d-138">地址不能由当前配置文件中的通讯簿提供程序处理。</span><span class="sxs-lookup"><span data-stu-id="be79d-138">The address cannot be handled by an address book provider in the current profile.</span></span>
    
<span data-ttu-id="be79d-139">有关详细信息，请参阅 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-139">For more information, see [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span>
  
<span data-ttu-id="be79d-140">客户端调用 **IAddrBook：：CreateOneOff** 为传入邮件上的地址创建一次条目标识符，当：</span><span class="sxs-lookup"><span data-stu-id="be79d-140">Clients call **IAddrBook::CreateOneOff** to create a one-off entry identifier for an address on an incoming message when:</span></span> 
  
- <span data-ttu-id="be79d-141">该地址的格式设置为一次地址。</span><span class="sxs-lookup"><span data-stu-id="be79d-141">The address is formatted as a one-off address.</span></span>
    
- <span data-ttu-id="be79d-142">地址的格式设置为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="be79d-142">The address is formatted as an Internet address.</span></span>
    
<span data-ttu-id="be79d-143">有关详细信息，请参阅 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-143">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md).</span></span>
  
<span data-ttu-id="be79d-144">有关一对一条目标识符和地址的信息，请参阅 [一次使用](one-off-entry-identifiers.md) 条目标识符和 [一次使用地址](one-off-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="be79d-144">For more information about one-off entry identifiers and addresses, see [One-Off Entry Identifiers](one-off-entry-identifiers.md) and [One-Off Addresses](one-off-addresses.md).</span></span>
  
<span data-ttu-id="be79d-145">收件人的属性是通讯簿属性和特定于收件人的属性的组合。</span><span class="sxs-lookup"><span data-stu-id="be79d-145">The properties of a recipient are a combination of address book properties and properties specific to recipients.</span></span> <span data-ttu-id="be79d-146">所有收件人都有基本地址属性，由通讯簿提供程序分配。</span><span class="sxs-lookup"><span data-stu-id="be79d-146">All recipients have the base address properties, assigned by address book providers.</span></span> <span data-ttu-id="be79d-147">当条目用作传出邮件的收件人时，基地址属性将复制到 **ADRLIST** 结构，该结构保留邮件的所有收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="be79d-147">When an entry is used as a recipient for an outgoing message, the base address properties are copied to the **ADRLIST** structure that holds the properties for all of a message's recipients.</span></span> 
  
<span data-ttu-id="be79d-148">专为收件人设置的两个属性是 PR_RECIPIENT_TYPE **和\*\*\*\*PR_RESPONSIBILITY**。</span><span class="sxs-lookup"><span data-stu-id="be79d-148">Two properties that are set specifically for recipients are **PR_RECIPIENT_TYPE** and **PR_RESPONSIBILITY**.</span></span> <span data-ttu-id="be79d-149">**PR_RECIPIENT_TYPE** 指示收件人是主要收件人、抄件抄稿人、盲信副本收件人还是重新发送收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-149">**PR_RECIPIENT_TYPE** indicates whether a recipient is a primary, carbon copy, blind carbon copy, or a resend recipient.</span></span> <span data-ttu-id="be79d-150">前三种类型分配给第一次发送的邮件上的收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-150">The first three types are assigned to recipients on messages that are being sent for the first time.</span></span> 
  
<span data-ttu-id="be79d-151">如果收件人未收到邮件，并尝试重新发送邮件，将复制该收件人，并且其类型设置为 MAPI_P1 以指示它是重新发送的收件人。</span><span class="sxs-lookup"><span data-stu-id="be79d-151">If a recipient does not receive the message and an attempt is made to resend it, the recipient is copied and its type is set to MAPI_P1 to indicate that it is a resend recipient.</span></span> <span data-ttu-id="be79d-152">如果只有部分收件人收到邮件，则 **PR_RECIPIENT_TYPE重新发送邮件** 时，会标记其 MAPI_SUBMITTED 属性。</span><span class="sxs-lookup"><span data-stu-id="be79d-152">If only some of the recipients receive a message, their **PR_RECIPIENT_TYPE** properties are marked with the addition of the MAPI_SUBMITTED flag when the message is resent.</span></span> <span data-ttu-id="be79d-153">客户端需要处理主要收件人，或将收件人的收件人 **PR_RECIPIENT_TYPE设置为** MAPI_TO。</span><span class="sxs-lookup"><span data-stu-id="be79d-153">Clients are required to handle primary recipients, or recipients with their **PR_RECIPIENT_TYPE** set to MAPI_TO.</span></span> <span data-ttu-id="be79d-154">所有其他类型都是可选的。</span><span class="sxs-lookup"><span data-stu-id="be79d-154">All other types are optional.</span></span> 
  
 <span data-ttu-id="be79d-155">**PR_RESPONSIBILITY** 设置为向传输提供程序指示它是否应该处理发送给收件人的发送。</span><span class="sxs-lookup"><span data-stu-id="be79d-155">**PR_RESPONSIBILITY** is set to indicate to the transport provider whether or not it should handle sending to the recipient.</span></span> <span data-ttu-id="be79d-156">首次发送传出邮件时，所有收件人 **PR_RESPONSIBILITY设置为** FALSE。</span><span class="sxs-lookup"><span data-stu-id="be79d-156">When an outgoing message is first sent, all of the recipients set **PR_RESPONSIBILITY** to FALSE.</span></span> <span data-ttu-id="be79d-157">作为传输提供程序声明向一个或多个收件人发送负责，其 **PR_RESPONSIBILITY属性设置为** TRUE。</span><span class="sxs-lookup"><span data-stu-id="be79d-157">As a transport provider claims responsibility for sending to one or more of the recipients, their **PR_RESPONSIBILITY** properties are set to TRUE.</span></span> 
  

