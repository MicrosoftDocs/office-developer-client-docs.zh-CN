---
title: MAPI 收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 88a4360d-6ab8-466e-8ebd-af80227ee00a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6af54b773b875531437a275f14c961a06ef799ff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569517"
---
# <a name="mapi-recipients"></a><span data-ttu-id="39dc0-103">MAPI 收件人</span><span class="sxs-lookup"><span data-stu-id="39dc0-103">MAPI Recipients</span></span>

  
  
<span data-ttu-id="39dc0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39dc0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39dc0-105">每个邮件传输有一个或多个收件人或一组描述其中是邮件传送的属性。</span><span class="sxs-lookup"><span data-stu-id="39dc0-105">Every message to be transmitted has one or more recipients, or a set of properties that describe where the message is to be delivered.</span></span> <span data-ttu-id="39dc0-106">仅在邮件的上下文中使用的收件人，因为它们被视为一条消息，而不是单独的 MAPI 对象的子对象。</span><span class="sxs-lookup"><span data-stu-id="39dc0-106">Because recipients are used only in the context of a message, they are considered subobjects of a message instead of separate MAPI objects.</span></span> <span data-ttu-id="39dc0-107">客户端和提供程序处理使用**IMessage**界面的收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-107">Clients and providers work with recipients using the **IMessage** interface.</span></span> <span data-ttu-id="39dc0-108">有关详细信息，请参阅[IMessage: IMAPIProp](imessageimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-108">For more information, see [IMessage : IMAPIProp](imessageimapiprop.md).</span></span>
  
<span data-ttu-id="39dc0-109">客户端通过其收件人表访问邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-109">Clients access a message's recipients through its recipient table.</span></span> <span data-ttu-id="39dc0-110">每个邮件有一个收件人的表，包含有关每个收件人的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="39dc0-110">Every message has a recipient table that contains summary information about each of its recipients.</span></span> <span data-ttu-id="39dc0-111">表中包括的列取决于邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="39dc0-111">The columns included in the table depend on the state of the message.</span></span> <span data-ttu-id="39dc0-112">在组合下一条消息时，其收件人可能具有仅三列表中：</span><span class="sxs-lookup"><span data-stu-id="39dc0-112">When a message is under composition, its recipients might have only three columns in the table:</span></span>
  
- <span data-ttu-id="39dc0-113">显示名称或**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="39dc0-113">Display name, or **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="39dc0-114">收件人类型或**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="39dc0-114">Recipient type, or **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="39dc0-115">行标识符或**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="39dc0-115">Row identifier, or **PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span></span>
    
<span data-ttu-id="39dc0-116">邮件已经过名称解析过程后，每个收件人将还具有条目标识符或**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 列。</span><span class="sxs-lookup"><span data-stu-id="39dc0-116">After the message has undergone the name resolution process, each recipient will also have an entry identifier, or **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) column.</span></span> <span data-ttu-id="39dc0-117">和收件人的表中的行时已提交邮件，将添加两个多个列：</span><span class="sxs-lookup"><span data-stu-id="39dc0-117">And when the message has been submitted, the rows in the recipient table will add two more columns:</span></span>
  
- <span data-ttu-id="39dc0-118">地址类型或**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="39dc0-118">Address type, or **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="39dc0-119">传输责任或**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="39dc0-119">Transport responsibility, or **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span></span>
    
<span data-ttu-id="39dc0-120">客户端可以通过调用其**IMessage::GetRecipientTable**方法或其**IMAPIProp::OpenProperty**方法检索邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="39dc0-120">Clients can retrieve a message's recipient table by calling its **IMessage::GetRecipientTable** method or its **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="39dc0-121">有关详细信息，请参阅[IMessage::GetRecipientTable](imessage-getrecipienttable.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-121">For more information, see [IMessage::GetRecipientTable](imessage-getrecipienttable.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="39dc0-122">消息存储提供程序需要支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="39dc0-122">Message store providers are expected to support both of these approaches.</span></span> <span data-ttu-id="39dc0-123">**OpenProperty**方法要求客户端界面标识符和**PR_MESSAGE_RECIPIENTS**为属性标记为指定 IID_IMAPITable。</span><span class="sxs-lookup"><span data-stu-id="39dc0-123">The **OpenProperty** approach requires that the client specify IID_IMAPITable as the interface identifier and **PR_MESSAGE_RECIPIENTS** as the property tag.</span></span> <span data-ttu-id="39dc0-124">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 是一个表示一条消息收件人表的表对象属性。</span><span class="sxs-lookup"><span data-stu-id="39dc0-124">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) is a table object property that represents a message's recipient table.</span></span> <span data-ttu-id="39dc0-125">消息存储提供程序所需设置**PR_MESSAGE_RECIPIENTS**关于每封邮件，并将其加入属性标记从**IMAPIProp::GetPropList**方法返回的数组。</span><span class="sxs-lookup"><span data-stu-id="39dc0-125">Message store providers are required to set **PR_MESSAGE_RECIPIENTS** for each message and include it in the array of property tags returned from the **IMAPIProp::GetPropList** method.</span></span> <span data-ttu-id="39dc0-126">有关详细信息，请参阅[IMAPIProp::GetPropList](imapiprop-getproplist.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-126">For more information, see [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span>
  
<span data-ttu-id="39dc0-127">有关如何使用收件人表的详细信息，请参阅[收件人表](recipient-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-127">For more information about how to work with a recipient table, see [Recipient Tables](recipient-tables.md).</span></span>
  
<span data-ttu-id="39dc0-128">除了要用于访问收件人表，可使用**PR_MESSAGE_RECIPIENTS** :</span><span class="sxs-lookup"><span data-stu-id="39dc0-128">In addition to being used to access a recipient table, **PR_MESSAGE_RECIPIENTS** can be used:</span></span> 
  
- <span data-ttu-id="39dc0-129">与**IMAPIProp::CopyTo**或**IMAPIProp::CopyProps**排除或包括收件人复制时。</span><span class="sxs-lookup"><span data-stu-id="39dc0-129">With **IMAPIProp::CopyTo** or **IMAPIProp::CopyProps** to exclude or include recipients when copying.</span></span> <span data-ttu-id="39dc0-130">有关详细信息，请参阅[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-130">For more information see, [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md).</span></span>
    
- <span data-ttu-id="39dc0-131">在以指示子限制应该将应用于收件人的子对象限制。</span><span class="sxs-lookup"><span data-stu-id="39dc0-131">In a subobject restriction to indicate that the child restiction should apply to recipients.</span></span>
    
<span data-ttu-id="39dc0-132">客户端可以将收件人添加到一条消息，通过复制 MAPI 通讯簿中的条目或创建新条目。</span><span class="sxs-lookup"><span data-stu-id="39dc0-132">Clients can add recipients to a message by copying entries from the MAPI address book or by creating new entries.</span></span> <span data-ttu-id="39dc0-133">调用 one-offs，这些新条目可以暂时存在，或可修改容器中永久保存。</span><span class="sxs-lookup"><span data-stu-id="39dc0-133">These new entries, called one-offs, can exist temporarily or be saved permanently in a modifiable container.</span></span> <span data-ttu-id="39dc0-134">虽然均摘自通讯簿的收件人有其通讯簿提供程序相关联的条目标识符，一次性收件人有条目标识符格式的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="39dc0-134">Whereas recipients that are taken from the address book have entry identifiers associated with their address book provider, one-off recipients have entry identifiers that are formatted by MAPI.</span></span> <span data-ttu-id="39dc0-135">传输提供程序和客户端关联一次性条目标识符与各种类型的地址。</span><span class="sxs-lookup"><span data-stu-id="39dc0-135">Transport providers and clients associate one-off entry identifiers with various types of addresses.</span></span> 
  
<span data-ttu-id="39dc0-136">传输提供程序调用**IMAPISupport::CreateOneOff**创建地址一次性条目标识符传出消息时：</span><span class="sxs-lookup"><span data-stu-id="39dc0-136">Transport providers call **IMAPISupport::CreateOneOff** to create a one-off entry identifier for an address on an outgoing message when:</span></span> 
  
- <span data-ttu-id="39dc0-137">网关所属的地址。</span><span class="sxs-lookup"><span data-stu-id="39dc0-137">The address belongs to a gateway.</span></span>
    
- <span data-ttu-id="39dc0-138">地址无法处理的当前配置文件中的地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="39dc0-138">The address cannot be handled by an address book provider in the current profile.</span></span>
    
<span data-ttu-id="39dc0-139">有关详细信息，请参阅[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-139">For more information, see [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span>
  
<span data-ttu-id="39dc0-140">客户端调用**IAddrBook::CreateOneOff**创建地址一次性条目标识符传入邮件时：</span><span class="sxs-lookup"><span data-stu-id="39dc0-140">Clients call **IAddrBook::CreateOneOff** to create a one-off entry identifier for an address on an incoming message when:</span></span> 
  
- <span data-ttu-id="39dc0-141">地址作为一次性地址格式。</span><span class="sxs-lookup"><span data-stu-id="39dc0-141">The address is formatted as a one-off address.</span></span>
    
- <span data-ttu-id="39dc0-142">地址的格式设置为 Internet 地址。</span><span class="sxs-lookup"><span data-stu-id="39dc0-142">The address is formatted as an Internet address.</span></span>
    
<span data-ttu-id="39dc0-143">有关详细信息，请参阅[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-143">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md).</span></span>
  
<span data-ttu-id="39dc0-144">有关一次性条目标识符和地址的详细信息，请参阅[一次性条目标识符](one-off-entry-identifiers.md)和[一次性地址](one-off-addresses.md)。</span><span class="sxs-lookup"><span data-stu-id="39dc0-144">For more information about one-off entry identifiers and addresses, see [One-Off Entry Identifiers](one-off-entry-identifiers.md) and [One-Off Addresses](one-off-addresses.md).</span></span>
  
<span data-ttu-id="39dc0-145">收件人的属性为通讯簿属性和属性特定于收件人的组合。</span><span class="sxs-lookup"><span data-stu-id="39dc0-145">The properties of a recipient are a combination of address book properties and properties specific to recipients.</span></span> <span data-ttu-id="39dc0-146">所有收件人都已分配的通讯簿提供程序的基址属性。</span><span class="sxs-lookup"><span data-stu-id="39dc0-146">All recipients have the base address properties, assigned by address book providers.</span></span> <span data-ttu-id="39dc0-147">当条目用作传出邮件收件人时，基址属性复制到包含属性的所有邮件的收件人的**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="39dc0-147">When an entry is used as a recipient for an outgoing message, the base address properties are copied to the **ADRLIST** structure that holds the properties for all of a message's recipients.</span></span> 
  
<span data-ttu-id="39dc0-148">专门为收件人的两个属性是**PR_RECIPIENT_TYPE**和**PR_RESPONSIBILITY**。</span><span class="sxs-lookup"><span data-stu-id="39dc0-148">Two properties that are set specifically for recipients are **PR_RECIPIENT_TYPE** and **PR_RESPONSIBILITY**.</span></span> <span data-ttu-id="39dc0-149">**PR_RECIPIENT_TYPE**指示收件人是主、 抄送、 密件抄送副本或重新发送收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-149">**PR_RECIPIENT_TYPE** indicates whether a recipient is a primary, carbon copy, blind carbon copy, or a resend recipient.</span></span> <span data-ttu-id="39dc0-150">前三种类型会分配到的第一次发送邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-150">The first three types are assigned to recipients on messages that are being sent for the first time.</span></span> 
  
<span data-ttu-id="39dc0-151">如果收件人不会收到邮件，并尝试重新发送它，复制收件人，并且其类型设置为 MAPI_P1，以指示它是重新发送收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-151">If a recipient does not receive the message and an attempt is made to resend it, the recipient is copied and its type is set to MAPI_P1 to indicate that it is a resend recipient.</span></span> <span data-ttu-id="39dc0-152">如果只有某些收件人收到一条消息，及其**PR_RECIPIENT_TYPE**属性标记并添加了 MAPI_SUBMITTED 标志时重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="39dc0-152">If only some of the recipients receive a message, their **PR_RECIPIENT_TYPE** properties are marked with the addition of the MAPI_SUBMITTED flag when the message is resent.</span></span> <span data-ttu-id="39dc0-153">客户端需要处理主收件人，或使用其**PR_RECIPIENT_TYPE**收件人为 MAPI_TO。</span><span class="sxs-lookup"><span data-stu-id="39dc0-153">Clients are required to handle primary recipients, or recipients with their **PR_RECIPIENT_TYPE** set to MAPI_TO.</span></span> <span data-ttu-id="39dc0-154">所有其他类型是可选的。</span><span class="sxs-lookup"><span data-stu-id="39dc0-154">All other types are optional.</span></span> 
  
 <span data-ttu-id="39dc0-155">**PR_RESPONSIBILITY**设置以指示到传输提供程序它应处理发送给收件人。</span><span class="sxs-lookup"><span data-stu-id="39dc0-155">**PR_RESPONSIBILITY** is set to indicate to the transport provider whether or not it should handle sending to the recipient.</span></span> <span data-ttu-id="39dc0-156">首先发送传出邮件时, 的所有收件人将**PR_RESPONSIBILITY**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="39dc0-156">When an outgoing message is first sent, all of the recipients set **PR_RESPONSIBILITY** to FALSE.</span></span> <span data-ttu-id="39dc0-157">传输提供程序声明责任发送到一个或多个收件人，及其**PR_RESPONSIBILITY**属性都设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="39dc0-157">As a transport provider claims responsibility for sending to one or more of the recipients, their **PR_RESPONSIBILITY** properties are set to TRUE.</span></span> 
  

