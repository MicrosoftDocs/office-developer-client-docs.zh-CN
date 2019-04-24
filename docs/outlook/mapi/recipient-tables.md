---
title: 收件人表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e77317-54c4-4fca-9ab4-835998ce07ce
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8950623308e85de1d239deb322f65ee867a33ca0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328418"
---
# <a name="recipient-tables"></a><span data-ttu-id="53664-103">收件人表</span><span class="sxs-lookup"><span data-stu-id="53664-103">Recipient Tables</span></span>

  
  
<span data-ttu-id="53664-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53664-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53664-105">收件人表包含有关邮件的所有收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="53664-105">The recipient table contains information about all the recipients for a message.</span></span> <span data-ttu-id="53664-106">邮件存储提供程序实现收件人表和客户端应用程序使用它们。</span><span class="sxs-lookup"><span data-stu-id="53664-106">Message store providers implement recipient tables and client applications use them.</span></span> <span data-ttu-id="53664-107">客户端通过调用[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法或在邮件存储区提供程序支持的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来访问收件人表。</span><span class="sxs-lookup"><span data-stu-id="53664-107">Clients access a recipient table by making a call to the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, or if the message store provider supports it, to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method.</span></span> <span data-ttu-id="53664-108">客户端通过为属性标记指定**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)), 并为接口标识符指定 IID_IMAPITable, 从而访问收件人表和**OpenProperty** 。</span><span class="sxs-lookup"><span data-stu-id="53664-108">Clients access recipient tables with **OpenProperty** by specifying **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) for the property tag and IID_IMAPITable for the interface identifier.</span></span> <span data-ttu-id="53664-109">可以通过调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法对收件人表进行更改。</span><span class="sxs-lookup"><span data-stu-id="53664-109">Changes to a recipient table can be made by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
<span data-ttu-id="53664-110">收件人表根据邮件是否已提交而设置了不同的列。</span><span class="sxs-lookup"><span data-stu-id="53664-110">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="53664-111">下列属性组成了在收件人表中设置的必需列:</span><span class="sxs-lookup"><span data-stu-id="53664-111">The following properties make up the required column set in recipient tables:</span></span>
  
- <span data-ttu-id="53664-112">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-112">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-113">**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-113">**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-114">**PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-114">**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span></span>
    
<span data-ttu-id="53664-115">可选属性为:</span><span class="sxs-lookup"><span data-stu-id="53664-115">The optional properties are:</span></span>
  
- <span data-ttu-id="53664-116">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-116">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-117">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-117">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-118">**PR_SPOOLER_STATUS**([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-118">**PR_SPOOLER_STATUS** ([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-119">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-119">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
<span data-ttu-id="53664-120">已提交的邮件应在其必需的列集中包含这些其他属性:</span><span class="sxs-lookup"><span data-stu-id="53664-120">Submitted messages should include these additional properties in their required column set:</span></span>
  
- <span data-ttu-id="53664-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="53664-122">**PR_RESPONSIBILITY**([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-122">**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span></span>
    
<span data-ttu-id="53664-123">根据提供程序的实现方式, 其他列 (如**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和[ENTRYID](entryid.md)) 可能位于表中。</span><span class="sxs-lookup"><span data-stu-id="53664-123">Depending on a provider's implementation, additional columns, such as **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) and [ENTRYID](entryid.md), might be in the table.</span></span>
  
<span data-ttu-id="53664-124">支持邮件传输的任何邮件存储提供程序, 如在提供程序的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置的 STORE_SUBMIT_OK 位所指示的那样, 应提供对一组特定类型的支持收件人表实现中的限制。</span><span class="sxs-lookup"><span data-stu-id="53664-124">Any message store provider that supports message transmission — as indicated by the STORE_SUBMIT_OK bit being set in the provider's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property — should offer support for a particular set of restrictions in a recipient table implementation.</span></span> <span data-ttu-id="53664-125">**and**、 **OR**、the 和 property 限制是对收件人表用户可用的限制的类型之一。</span><span class="sxs-lookup"><span data-stu-id="53664-125">The **AND**, **OR**, exist, and property restrictions are among the types of restrictions that should be available to recipient table users.</span></span> <span data-ttu-id="53664-126">在属性限制中, 只需支持等号运算符和不相等运算符。</span><span class="sxs-lookup"><span data-stu-id="53664-126">Only the equal and not equal operators need to be supported on the property restriction.</span></span> <span data-ttu-id="53664-127">这些限制必须与下列属性一起使用:</span><span class="sxs-lookup"><span data-stu-id="53664-127">These restrictions must work with the following properties:</span></span>
  
- <span data-ttu-id="53664-128">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="53664-128">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="53664-129">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53664-129">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="53664-130">**PR_RECIPIENT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="53664-130">**PR_RECIPIENT_TYPE**</span></span>
    
- <span data-ttu-id="53664-131">**PR_RESPONSIBILITY**</span><span class="sxs-lookup"><span data-stu-id="53664-131">**PR_RESPONSIBILITY**</span></span>
    
- <span data-ttu-id="53664-132">**PR_SPOOLER_STATUS**</span><span class="sxs-lookup"><span data-stu-id="53664-132">**PR_SPOOLER_STATUS**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="53664-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53664-133">See also</span></span>



[<span data-ttu-id="53664-134">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="53664-134">MAPI Tables</span></span>](mapi-tables.md)

