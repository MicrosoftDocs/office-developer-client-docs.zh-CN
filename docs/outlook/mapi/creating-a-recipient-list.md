---
title: 创建收件人列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 270f86dd-2c1f-47eb-80f7-9d0d63936d61
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6de805da2aadd8ac40ca984c5f336d5ca7906248
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590125"
---
# <a name="creating-a-recipient-list"></a><span data-ttu-id="77d10-103">创建收件人列表</span><span class="sxs-lookup"><span data-stu-id="77d10-103">Creating a Recipient List</span></span>

  
  
<span data-ttu-id="77d10-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="77d10-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="77d10-105">收件人列表是每个邮件收件人中包含的属性值结构数组[ADRLIST](adrlist.md)结构 — 目标的邮件。</span><span class="sxs-lookup"><span data-stu-id="77d10-105">A recipient list is an [ADRLIST](adrlist.md) structure that contains an array of property value structures for each message recipient — destination for the message.</span></span> <span data-ttu-id="77d10-106">收件人可以表示 human 用户、 计算机或文件夹。</span><span class="sxs-lookup"><span data-stu-id="77d10-106">A recipient can represent a human user, a machine, or a folder.</span></span> <span data-ttu-id="77d10-107">要发送的所有邮件都需要至少一个收件人的已通过名称解析过程的 — 确保**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的收件人的属性值数组中包含的过程。</span><span class="sxs-lookup"><span data-stu-id="77d10-107">All messages to be sent require at least one recipient that has been through the name resolution process — a process for ensuring that the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property is included in the recipient's property value array.</span></span> 
  
<span data-ttu-id="77d10-108">收件人的属性为通讯簿属性和邮件属性的组合。</span><span class="sxs-lookup"><span data-stu-id="77d10-108">The properties of a recipient are a combination of address book properties and message properties.</span></span> <span data-ttu-id="77d10-109">收件人属性可应用于所有邮件的特定收件人或仅对当前邮件。</span><span class="sxs-lookup"><span data-stu-id="77d10-109">Recipient properties can apply either to all messages for a particular recipient or only to the current message.</span></span> <span data-ttu-id="77d10-110">同时消息存储和传输提供程序可以设置收件人属性。</span><span class="sxs-lookup"><span data-stu-id="77d10-110">Both message store and transport providers can set recipient properties.</span></span> 
  
<span data-ttu-id="77d10-111">已准备好发送邮件时，每个收件人必须其属性值阵列中有一组核心属性。</span><span class="sxs-lookup"><span data-stu-id="77d10-111">Each recipient must have a core set of properties in its property value array by the time the message is ready to be sent.</span></span> <span data-ttu-id="77d10-112">组所需的收件人属性包括：</span><span class="sxs-lookup"><span data-stu-id="77d10-112">The required set of recipient properties include:</span></span>
  
- <span data-ttu-id="77d10-113">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77d10-113">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="77d10-114">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77d10-114">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span> 
    
- <span data-ttu-id="77d10-115">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77d10-115">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="77d10-116">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="77d10-116">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="77d10-117">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77d10-117">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="77d10-118">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77d10-118">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="77d10-119">访问收件人、 向其发送消息和要与其他人使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="77d10-119">These properties are used to access the recipient, send messages to it, and to compare it to others.</span></span> <span data-ttu-id="77d10-120">并非所有这些属性所要立即可用。</span><span class="sxs-lookup"><span data-stu-id="77d10-120">Not all of these properties need to be available right away.</span></span> <span data-ttu-id="77d10-121">您可以添加收件人最初不知道其条目标识符，依赖于名称解析过程分配此属性。</span><span class="sxs-lookup"><span data-stu-id="77d10-121">You can add a recipient initially without knowing its entry identifier, relying on the name resolution process to assign this property.</span></span> <span data-ttu-id="77d10-122">某个时刻发送一条消息之前，请调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)以确保所有收件人列表中的收件人解析。</span><span class="sxs-lookup"><span data-stu-id="77d10-122">At some point before you send a message, call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to make sure that all of the recipients in your recipient list are resolved.</span></span> <span data-ttu-id="77d10-123">有关详细信息，请参阅[解析收件人姓名](resolving-a-recipient-name.md)。</span><span class="sxs-lookup"><span data-stu-id="77d10-123">For more information, see [Resolving a Recipient Name](resolving-a-recipient-name.md).</span></span>
  
<span data-ttu-id="77d10-124">从消息用户或通讯簿容器中的通讯组列表项或 one-offs，可以创建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="77d10-124">Recipient lists can be created from messaging users or distribution list entries in an address book container or from one-offs.</span></span> <span data-ttu-id="77d10-125">One-offs 是作为临时条目只能用于解决单个邮件或条目添加到个人通讯簿创建的收件人。</span><span class="sxs-lookup"><span data-stu-id="77d10-125">One-offs are recipients that are created either as temporary entries to be used only for addressing a single message or as entries to be added to a personal address book.</span></span> <span data-ttu-id="77d10-126">一次性条目标识符和地址的格式由 MAPI 定义。</span><span class="sxs-lookup"><span data-stu-id="77d10-126">The format for a one-off entry identifier and address is defined by MAPI.</span></span> <span data-ttu-id="77d10-127">有关这些格式的详细信息，请参阅[一次性地址](one-off-addresses.md)和[一次性条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="77d10-127">For more information about these formats, see [One-Off Addresses](one-off-addresses.md) and [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span>
  
<span data-ttu-id="77d10-128">您可以让用户能够构建其收件人列表：</span><span class="sxs-lookup"><span data-stu-id="77d10-128">You can enable users to build their recipient lists:</span></span>
  
- <span data-ttu-id="77d10-129">仅与通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="77d10-129">Only with entries from the address book.</span></span>
    
- <span data-ttu-id="77d10-130">仅与一次性条目。</span><span class="sxs-lookup"><span data-stu-id="77d10-130">Only with one-off entries.</span></span>
    
- <span data-ttu-id="77d10-131">与通讯簿收件人和 one-offs 的组合。</span><span class="sxs-lookup"><span data-stu-id="77d10-131">With a combination of address book recipients and one-offs.</span></span>
    
 <span data-ttu-id="77d10-132">**创建使用通用的地址对话框的收件人列表**</span><span class="sxs-lookup"><span data-stu-id="77d10-132">**To create a recipient list using the common address dialog box**</span></span>
  
1. <span data-ttu-id="77d10-133">分配[ADRPARM](adrparm.md)结构和指向[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="77d10-133">Allocate an [ADRPARM](adrparm.md) structure and a pointer to an [ADRLIST](adrlist.md) structure.</span></span> 
    
2. <span data-ttu-id="77d10-134">零**ADRPARM**结构中的内存和**ADRLIST**指针设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="77d10-134">Zero the memory in the **ADRPARM** structure and set the **ADRLIST** pointer to NULL.</span></span> 
    
3. <span data-ttu-id="77d10-135">调用[IAddrBook::Address](iaddrbook-address.md)显示地址对话框并填充**ADRPARM**结构。</span><span class="sxs-lookup"><span data-stu-id="77d10-135">Call [IAddrBook::Address](iaddrbook-address.md) to display the address dialog box and populate the **ADRPARM** structure.</span></span> 
    
4. <span data-ttu-id="77d10-136">调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)，传递**ADRLIST**指针。</span><span class="sxs-lookup"><span data-stu-id="77d10-136">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md), passing the **ADRLIST** pointer.</span></span> <span data-ttu-id="77d10-137">此结构将包含每个用户所选定的收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="77d10-137">This structure will contain the properties of each of the recipients selected by the user.</span></span> 
    
 <span data-ttu-id="77d10-138">**以编程方式创建收件人列表**</span><span class="sxs-lookup"><span data-stu-id="77d10-138">**To create a recipient list programmatically**</span></span>
  
1. <span data-ttu-id="77d10-139">分配**ADRLIST**结构，其中包含每个收件人包含在列表中的一个[ADRENTRY](adrentry.md)结构。</span><span class="sxs-lookup"><span data-stu-id="77d10-139">Allocate an **ADRLIST** structure that contains one [ADRENTRY](adrentry.md) structure for each of the recipients to be included in the list.</span></span> <span data-ttu-id="77d10-140">使每个**ADRENTRY**结构足以容纳每个必需的属性和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="77d10-140">Make each **ADRENTRY** structure large enough to hold each of the required properties and **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)).</span></span>
    
2. <span data-ttu-id="77d10-141">对于每个收件人，设置**ADRLIST**结构及其**aEntries**成员属性值数组。</span><span class="sxs-lookup"><span data-stu-id="77d10-141">For each recipient, set the property value array for its **aEntries** member in the **ADRLIST** structure.</span></span> 
    
3. <span data-ttu-id="77d10-142">调用设置了 MODRECIP_ADD 标志[IMessage::ModifyRecipients](imessage-modifyrecipients.md) 。</span><span class="sxs-lookup"><span data-stu-id="77d10-142">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md) with the MODRECIP_ADD flag set.</span></span> 
    

