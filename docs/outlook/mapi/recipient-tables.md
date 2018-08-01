---
title: 收件人表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e77317-54c4-4fca-9ab4-835998ce07ce
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cc7635c474b99898d59589f33fcf06cf24697378
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778591"
---
# <a name="recipient-tables"></a><span data-ttu-id="7ec55-103">收件人表</span><span class="sxs-lookup"><span data-stu-id="7ec55-103">Recipient Tables</span></span>

  
  
<span data-ttu-id="7ec55-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7ec55-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7ec55-105">收件人表包含有关所有邮件的收件人信息。</span><span class="sxs-lookup"><span data-stu-id="7ec55-105">The recipient table contains information about all the recipients for a message.</span></span> <span data-ttu-id="7ec55-106">消息存储提供程序实现收件人表，客户端应用程序使用它们。</span><span class="sxs-lookup"><span data-stu-id="7ec55-106">Message store providers implement recipient tables and client applications use them.</span></span> <span data-ttu-id="7ec55-107">客户端通过[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法调用访问收件人的表或消息存储提供程序是否支持， [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7ec55-107">Clients access a recipient table by making a call to the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, or if the message store provider supports it, to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method.</span></span> <span data-ttu-id="7ec55-108">客户端访问收件人表与**OpenProperty**通过为接口标识符属性标记和 IID_IMAPITable 指定**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="7ec55-108">Clients access recipient tables with **OpenProperty** by specifying **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) for the property tag and IID_IMAPITable for the interface identifier.</span></span> <span data-ttu-id="7ec55-109">可以通过调用[IMessage::ModifyRecipients](imessage-modifyrecipients.md)方法来发出对收件人的表的更改。</span><span class="sxs-lookup"><span data-stu-id="7ec55-109">Changes to a recipient table can be made by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
<span data-ttu-id="7ec55-110">收件人表具有一个不同的列，具体取决于是否已提交邮件设置。</span><span class="sxs-lookup"><span data-stu-id="7ec55-110">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="7ec55-111">以下属性构成收件人表中所需的列：</span><span class="sxs-lookup"><span data-stu-id="7ec55-111">The following properties make up the required column set in recipient tables:</span></span>
  
- <span data-ttu-id="7ec55-112">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-112">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-113">**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-113">**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-114">**PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-114">**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span></span>
    
<span data-ttu-id="7ec55-115">可选属性包括：</span><span class="sxs-lookup"><span data-stu-id="7ec55-115">The optional properties are:</span></span>
  
- <span data-ttu-id="7ec55-116">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-116">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-117">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-117">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-118">**PR_SPOOLER_STATUS**([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-118">**PR_SPOOLER_STATUS** ([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-119">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-119">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
<span data-ttu-id="7ec55-120">提交的邮件应在其所需的列集包含这些其他属性：</span><span class="sxs-lookup"><span data-stu-id="7ec55-120">Submitted messages should include these additional properties in their required column set:</span></span>
  
- <span data-ttu-id="7ec55-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="7ec55-122">**PR_RESPONSIBILITY**([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-122">**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span></span>
    
<span data-ttu-id="7ec55-123">具体取决于提供程序的实现，附加列，如**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和[ENTRYID](entryid.md)，可能表中。</span><span class="sxs-lookup"><span data-stu-id="7ec55-123">Depending on a provider's implementation, additional columns, such as **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) and [ENTRYID](entryid.md), might be in the table.</span></span>
  
<span data-ttu-id="7ec55-124">支持消息传输任何消息存储提供程序 — 由提供商的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中所设置的 STORE_SUBMIT_OK 位 — 应提供一组特定的支持在收件人表实现的限制。</span><span class="sxs-lookup"><span data-stu-id="7ec55-124">Any message store provider that supports message transmission — as indicated by the STORE_SUBMIT_OK bit being set in the provider's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property — should offer support for a particular set of restrictions in a recipient table implementation.</span></span> <span data-ttu-id="7ec55-125">**AND**、**或**，存在，并且属性限制是应为可供收件人表用户的限制的类型。</span><span class="sxs-lookup"><span data-stu-id="7ec55-125">The **AND**, **OR**, exist, and property restrictions are among the types of restrictions that should be available to recipient table users.</span></span> <span data-ttu-id="7ec55-126">只有等于和不等于运算符需要支持在属性限制。</span><span class="sxs-lookup"><span data-stu-id="7ec55-126">Only the equal and not equal operators need to be supported on the property restriction.</span></span> <span data-ttu-id="7ec55-127">这些限制必须使用以下属性：</span><span class="sxs-lookup"><span data-stu-id="7ec55-127">These restrictions must work with the following properties:</span></span>
  
- <span data-ttu-id="7ec55-128">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="7ec55-128">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="7ec55-129">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="7ec55-129">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="7ec55-130">**PR_RECIPIENT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="7ec55-130">**PR_RECIPIENT_TYPE**</span></span>
    
- <span data-ttu-id="7ec55-131">**PR_RESPONSIBILITY**</span><span class="sxs-lookup"><span data-stu-id="7ec55-131">**PR_RESPONSIBILITY**</span></span>
    
- <span data-ttu-id="7ec55-132">**PR_SPOOLER_STATUS**</span><span class="sxs-lookup"><span data-stu-id="7ec55-132">**PR_SPOOLER_STATUS**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7ec55-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ec55-133">See also</span></span>



[<span data-ttu-id="7ec55-134">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="7ec55-134">MAPI Tables</span></span>](mapi-tables.md)

