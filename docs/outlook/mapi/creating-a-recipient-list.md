---
title: 创建收件人列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 270f86dd-2c1f-47eb-80f7-9d0d63936d61
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e3aa1f2b2e1e7c6d8a9be3fff451002952930ffb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428212"
---
# <a name="creating-a-recipient-list"></a><span data-ttu-id="0132e-103">创建收件人列表</span><span class="sxs-lookup"><span data-stu-id="0132e-103">Creating a Recipient List</span></span>

  
  
<span data-ttu-id="0132e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0132e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0132e-105">收件人列表是一个 [ADRLIST](adrlist.md) 结构，包含每个邮件收件人的属性值结构数组 — 邮件的目标。</span><span class="sxs-lookup"><span data-stu-id="0132e-105">A recipient list is an [ADRLIST](adrlist.md) structure that contains an array of property value structures for each message recipient — destination for the message.</span></span> <span data-ttu-id="0132e-106">收件人可以代表用户、计算机或文件夹。</span><span class="sxs-lookup"><span data-stu-id="0132e-106">A recipient can represent a human user, a machine, or a folder.</span></span> <span data-ttu-id="0132e-107">要发送的所有邮件都至少需要一个已执行名称解析过程的收件人， 这是确保 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性包含在收件人的属性值数组中的过程。</span><span class="sxs-lookup"><span data-stu-id="0132e-107">All messages to be sent require at least one recipient that has been through the name resolution process — a process for ensuring that the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property is included in the recipient's property value array.</span></span> 
  
<span data-ttu-id="0132e-108">收件人的属性是通讯簿属性和邮件属性的组合。</span><span class="sxs-lookup"><span data-stu-id="0132e-108">The properties of a recipient are a combination of address book properties and message properties.</span></span> <span data-ttu-id="0132e-109">收件人属性可以应用于特定收件人的所有邮件，也可以只应用于当前邮件。</span><span class="sxs-lookup"><span data-stu-id="0132e-109">Recipient properties can apply either to all messages for a particular recipient or only to the current message.</span></span> <span data-ttu-id="0132e-110">邮件存储和传输提供程序都可以设置收件人属性。</span><span class="sxs-lookup"><span data-stu-id="0132e-110">Both message store and transport providers can set recipient properties.</span></span> 
  
<span data-ttu-id="0132e-111">在准备好发送邮件时，每个收件人的属性值数组中都必须有一组核心属性。</span><span class="sxs-lookup"><span data-stu-id="0132e-111">Each recipient must have a core set of properties in its property value array by the time the message is ready to be sent.</span></span> <span data-ttu-id="0132e-112">所需的收件人属性集包括：</span><span class="sxs-lookup"><span data-stu-id="0132e-112">The required set of recipient properties include:</span></span>
  
- <span data-ttu-id="0132e-113">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0132e-113">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="0132e-114">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0132e-114">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span> 
    
- <span data-ttu-id="0132e-115">**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="0132e-115">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="0132e-116">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="0132e-116">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="0132e-117">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0132e-117">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="0132e-118">**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="0132e-118">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="0132e-119">这些属性用于访问收件人、向收件人发送邮件以及将其与其他收件人进行比较。</span><span class="sxs-lookup"><span data-stu-id="0132e-119">These properties are used to access the recipient, send messages to it, and to compare it to others.</span></span> <span data-ttu-id="0132e-120">并非所有这些属性都需要马上可用。</span><span class="sxs-lookup"><span data-stu-id="0132e-120">Not all of these properties need to be available right away.</span></span> <span data-ttu-id="0132e-121">您可以最初添加收件人，而无需知道其条目标识符，而依赖名称解析过程来分配此属性。</span><span class="sxs-lookup"><span data-stu-id="0132e-121">You can add a recipient initially without knowing its entry identifier, relying on the name resolution process to assign this property.</span></span> <span data-ttu-id="0132e-122">在发送邮件之前，请调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 以确保收件人列表中的所有收件人已解析。</span><span class="sxs-lookup"><span data-stu-id="0132e-122">At some point before you send a message, call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to make sure that all of the recipients in your recipient list are resolved.</span></span> <span data-ttu-id="0132e-123">有关详细信息，请参阅 [解析收件人姓名](resolving-a-recipient-name.md)。</span><span class="sxs-lookup"><span data-stu-id="0132e-123">For more information, see [Resolving a Recipient Name](resolving-a-recipient-name.md).</span></span>
  
<span data-ttu-id="0132e-124">收件人列表可以从通讯簿容器中的邮件用户或通讯组列表条目创建，也可以从一次发送创建。</span><span class="sxs-lookup"><span data-stu-id="0132e-124">Recipient lists can be created from messaging users or distribution list entries in an address book container or from one-offs.</span></span> <span data-ttu-id="0132e-125">一对多是作为临时条目创建的收件人，仅用于处理单个邮件，或创建为要添加到个人通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="0132e-125">One-offs are recipients that are created either as temporary entries to be used only for addressing a single message or as entries to be added to a personal address book.</span></span> <span data-ttu-id="0132e-126">一次输入标识符和地址的格式由 MAPI 定义。</span><span class="sxs-lookup"><span data-stu-id="0132e-126">The format for a one-off entry identifier and address is defined by MAPI.</span></span> <span data-ttu-id="0132e-127">有关这些格式的信息，请参阅 [一次使用](one-off-addresses.md) 地址和 [一次使用条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="0132e-127">For more information about these formats, see [One-Off Addresses](one-off-addresses.md) and [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span>
  
<span data-ttu-id="0132e-128">您可以允许用户构建其收件人列表：</span><span class="sxs-lookup"><span data-stu-id="0132e-128">You can enable users to build their recipient lists:</span></span>
  
- <span data-ttu-id="0132e-129">仅包含通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="0132e-129">Only with entries from the address book.</span></span>
    
- <span data-ttu-id="0132e-130">仅包含一次输入。</span><span class="sxs-lookup"><span data-stu-id="0132e-130">Only with one-off entries.</span></span>
    
- <span data-ttu-id="0132e-131">结合使用通讯簿收件人和一键式。</span><span class="sxs-lookup"><span data-stu-id="0132e-131">With a combination of address book recipients and one-offs.</span></span>
    
 <span data-ttu-id="0132e-132">**使用公用地址对话框创建收件人列表**</span><span class="sxs-lookup"><span data-stu-id="0132e-132">**To create a recipient list using the common address dialog box**</span></span>
  
1. <span data-ttu-id="0132e-133">分配 [ADRPARM](adrparm.md) 结构和指向 [ADRLIST](adrlist.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="0132e-133">Allocate an [ADRPARM](adrparm.md) structure and a pointer to an [ADRLIST](adrlist.md) structure.</span></span> 
    
2. <span data-ttu-id="0132e-134">将 **ADRPARM** 结构中的内存清零，将 **ADRLIST** 指针设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0132e-134">Zero the memory in the **ADRPARM** structure and set the **ADRLIST** pointer to NULL.</span></span> 
    
3. <span data-ttu-id="0132e-135">调用 [IAddrBook：：Address](iaddrbook-address.md) 以显示地址对话框并填充 **ADRPARM** 结构。</span><span class="sxs-lookup"><span data-stu-id="0132e-135">Call [IAddrBook::Address](iaddrbook-address.md) to display the address dialog box and populate the **ADRPARM** structure.</span></span> 
    
4. <span data-ttu-id="0132e-136">调用 [IMessage：：ModifyRecipients，](imessage-modifyrecipients.md)传递 **ADRLIST** 指针。</span><span class="sxs-lookup"><span data-stu-id="0132e-136">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md), passing the **ADRLIST** pointer.</span></span> <span data-ttu-id="0132e-137">此结构将包含用户选择的每个收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="0132e-137">This structure will contain the properties of each of the recipients selected by the user.</span></span> 
    
 <span data-ttu-id="0132e-138">**以编程方式创建收件人列表**</span><span class="sxs-lookup"><span data-stu-id="0132e-138">**To create a recipient list programmatically**</span></span>
  
1. <span data-ttu-id="0132e-139">为要包含在列表中的每个收件人分配包含一个 [ADRENTRY](adrentry.md)结构的 **ADRLIST** 结构。</span><span class="sxs-lookup"><span data-stu-id="0132e-139">Allocate an **ADRLIST** structure that contains one [ADRENTRY](adrentry.md) structure for each of the recipients to be included in the list.</span></span> <span data-ttu-id="0132e-140">使每个 **ADRENTRY** 结构足够大，以容纳每个必需的属性PR_RECIPIENT_TYPE ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="0132e-140">Make each **ADRENTRY** structure large enough to hold each of the required properties and **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)).</span></span>
    
2. <span data-ttu-id="0132e-141">对于每个收件人，在 **ADRLIST** 结构中设置 **其 aEntries** 成员属性值数组。</span><span class="sxs-lookup"><span data-stu-id="0132e-141">For each recipient, set the property value array for its **aEntries** member in the **ADRLIST** structure.</span></span> 
    
3. <span data-ttu-id="0132e-142">调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 并设置MODRECIP_ADD标志。</span><span class="sxs-lookup"><span data-stu-id="0132e-142">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md) with the MODRECIP_ADD flag set.</span></span> 
    

