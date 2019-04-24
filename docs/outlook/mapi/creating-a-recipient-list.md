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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332905"
---
# <a name="creating-a-recipient-list"></a><span data-ttu-id="aaa70-103">创建收件人列表</span><span class="sxs-lookup"><span data-stu-id="aaa70-103">Creating a Recipient List</span></span>

  
  
<span data-ttu-id="aaa70-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aaa70-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aaa70-105">收件人列表是一个[ADRLIST](adrlist.md)结构, 其中包含每个邮件收件人的属性值结构的数组, 邮件的目标地址。</span><span class="sxs-lookup"><span data-stu-id="aaa70-105">A recipient list is an [ADRLIST](adrlist.md) structure that contains an array of property value structures for each message recipient — destination for the message.</span></span> <span data-ttu-id="aaa70-106">收件人可以代表人为用户、计算机或文件夹。</span><span class="sxs-lookup"><span data-stu-id="aaa70-106">A recipient can represent a human user, a machine, or a folder.</span></span> <span data-ttu-id="aaa70-107">要发送的所有邮件都至少需要一个经过名称解析过程的收件人, 这是一个用于确保**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性包含在收件人的属性值数组中的过程。</span><span class="sxs-lookup"><span data-stu-id="aaa70-107">All messages to be sent require at least one recipient that has been through the name resolution process — a process for ensuring that the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property is included in the recipient's property value array.</span></span> 
  
<span data-ttu-id="aaa70-108">收件人的属性是通讯簿属性和邮件属性的组合。</span><span class="sxs-lookup"><span data-stu-id="aaa70-108">The properties of a recipient are a combination of address book properties and message properties.</span></span> <span data-ttu-id="aaa70-109">收件人属性可以应用于特定收件人的所有邮件, 也可以仅适用于当前邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa70-109">Recipient properties can apply either to all messages for a particular recipient or only to the current message.</span></span> <span data-ttu-id="aaa70-110">邮件存储和传输提供程序都可以设置收件人属性。</span><span class="sxs-lookup"><span data-stu-id="aaa70-110">Both message store and transport providers can set recipient properties.</span></span> 
  
<span data-ttu-id="aaa70-111">每个收件人都必须在其属性值数组中包含一组核心属性 (通过准备发送邮件的时间)。</span><span class="sxs-lookup"><span data-stu-id="aaa70-111">Each recipient must have a core set of properties in its property value array by the time the message is ready to be sent.</span></span> <span data-ttu-id="aaa70-112">所需的一组收件人属性包括:</span><span class="sxs-lookup"><span data-stu-id="aaa70-112">The required set of recipient properties include:</span></span>
  
- <span data-ttu-id="aaa70-113">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="aaa70-113">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="aaa70-114">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="aaa70-114">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span> 
    
- <span data-ttu-id="aaa70-115">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="aaa70-115">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="aaa70-116">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="aaa70-116">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="aaa70-117">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="aaa70-117">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span> 
    
- <span data-ttu-id="aaa70-118">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="aaa70-118">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="aaa70-119">这些属性用于访问收件人、向其发送邮件, 并将其与其他人进行比较。</span><span class="sxs-lookup"><span data-stu-id="aaa70-119">These properties are used to access the recipient, send messages to it, and to compare it to others.</span></span> <span data-ttu-id="aaa70-120">并不是所有这些属性都需要立即可用。</span><span class="sxs-lookup"><span data-stu-id="aaa70-120">Not all of these properties need to be available right away.</span></span> <span data-ttu-id="aaa70-121">您可以在不知道其条目标识符的情况下, 开始添加收件人, 并依靠名称解析过程来分配该属性。</span><span class="sxs-lookup"><span data-stu-id="aaa70-121">You can add a recipient initially without knowing its entry identifier, relying on the name resolution process to assign this property.</span></span> <span data-ttu-id="aaa70-122">在发送邮件之前的某个时刻, 调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)以确保收件人列表中的所有收件人均已解析。</span><span class="sxs-lookup"><span data-stu-id="aaa70-122">At some point before you send a message, call [IAddrBook::ResolveName](iaddrbook-resolvename.md) to make sure that all of the recipients in your recipient list are resolved.</span></span> <span data-ttu-id="aaa70-123">有关详细信息, 请参阅[解析收件人姓名](resolving-a-recipient-name.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa70-123">For more information, see [Resolving a Recipient Name](resolving-a-recipient-name.md).</span></span>
  
<span data-ttu-id="aaa70-124">收件人列表可以从通讯簿容器中的邮件用户或通讯组列表条目中创建, 也可以通过一次阻止。</span><span class="sxs-lookup"><span data-stu-id="aaa70-124">Recipient lists can be created from messaging users or distribution list entries in an address book container or from one-offs.</span></span> <span data-ttu-id="aaa70-125">一种方法是创建为仅用于寻址单个邮件或作为要添加到个人通讯簿的条目的临时条目的收件人。</span><span class="sxs-lookup"><span data-stu-id="aaa70-125">One-offs are recipients that are created either as temporary entries to be used only for addressing a single message or as entries to be added to a personal address book.</span></span> <span data-ttu-id="aaa70-126">一次性条目标识符和地址的格式由 MAPI 定义。</span><span class="sxs-lookup"><span data-stu-id="aaa70-126">The format for a one-off entry identifier and address is defined by MAPI.</span></span> <span data-ttu-id="aaa70-127">有关这些格式的详细信息, 请参阅[一次性地址](one-off-addresses.md)和[一次性条目标识符](one-off-entry-identifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa70-127">For more information about these formats, see [One-Off Addresses](one-off-addresses.md) and [One-Off Entry Identifiers](one-off-entry-identifiers.md).</span></span>
  
<span data-ttu-id="aaa70-128">您可以允许用户生成其收件人列表:</span><span class="sxs-lookup"><span data-stu-id="aaa70-128">You can enable users to build their recipient lists:</span></span>
  
- <span data-ttu-id="aaa70-129">仅包含通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="aaa70-129">Only with entries from the address book.</span></span>
    
- <span data-ttu-id="aaa70-130">仅限一次性条目。</span><span class="sxs-lookup"><span data-stu-id="aaa70-130">Only with one-off entries.</span></span>
    
- <span data-ttu-id="aaa70-131">组合使用通讯簿收件人和一次性。</span><span class="sxs-lookup"><span data-stu-id="aaa70-131">With a combination of address book recipients and one-offs.</span></span>
    
 <span data-ttu-id="aaa70-132">**使用 "公用地址" 对话框创建收件人列表**</span><span class="sxs-lookup"><span data-stu-id="aaa70-132">**To create a recipient list using the common address dialog box**</span></span>
  
1. <span data-ttu-id="aaa70-133">分配一个[ADRPARM](adrparm.md)结构和一个指向[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="aaa70-133">Allocate an [ADRPARM](adrparm.md) structure and a pointer to an [ADRLIST](adrlist.md) structure.</span></span> 
    
2. <span data-ttu-id="aaa70-134">零**ADRPARM**结构中的内存, 并将**ADRLIST**指针设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="aaa70-134">Zero the memory in the **ADRPARM** structure and set the **ADRLIST** pointer to NULL.</span></span> 
    
3. <span data-ttu-id="aaa70-135">调用[IAddrBook:: address](iaddrbook-address.md)以显示地址对话框并填充**ADRPARM**结构。</span><span class="sxs-lookup"><span data-stu-id="aaa70-135">Call [IAddrBook::Address](iaddrbook-address.md) to display the address dialog box and populate the **ADRPARM** structure.</span></span> 
    
4. <span data-ttu-id="aaa70-136">调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md), 并传递**ADRLIST**指针。</span><span class="sxs-lookup"><span data-stu-id="aaa70-136">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md), passing the **ADRLIST** pointer.</span></span> <span data-ttu-id="aaa70-137">此结构将包含用户选择的每个收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="aaa70-137">This structure will contain the properties of each of the recipients selected by the user.</span></span> 
    
 <span data-ttu-id="aaa70-138">**以编程方式创建收件人列表**</span><span class="sxs-lookup"><span data-stu-id="aaa70-138">**To create a recipient list programmatically**</span></span>
  
1. <span data-ttu-id="aaa70-139">为要包含在列表中的每个收件人分配包含一个[ADRENTRY](adrentry.md)结构的**ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="aaa70-139">Allocate an **ADRLIST** structure that contains one [ADRENTRY](adrentry.md) structure for each of the recipients to be included in the list.</span></span> <span data-ttu-id="aaa70-140">使每个**ADRENTRY**结构都足够大, 以容纳每个必需的属性和**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="aaa70-140">Make each **ADRENTRY** structure large enough to hold each of the required properties and **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)).</span></span>
    
2. <span data-ttu-id="aaa70-141">对于每个收件人, 在**ADRLIST**结构中为其**aEntries**成员设置属性值数组。</span><span class="sxs-lookup"><span data-stu-id="aaa70-141">For each recipient, set the property value array for its **aEntries** member in the **ADRLIST** structure.</span></span> 
    
3. <span data-ttu-id="aaa70-142">调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)并设置 MODRECIP_ADD 标志。</span><span class="sxs-lookup"><span data-stu-id="aaa70-142">Call [IMessage::ModifyRecipients](imessage-modifyrecipients.md) with the MODRECIP_ADD flag set.</span></span> 
    

