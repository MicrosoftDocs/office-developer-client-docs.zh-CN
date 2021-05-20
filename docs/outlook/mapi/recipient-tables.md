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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437285"
---
# <a name="recipient-tables"></a><span data-ttu-id="6b4d0-103">收件人表</span><span class="sxs-lookup"><span data-stu-id="6b4d0-103">Recipient Tables</span></span>

  
  
<span data-ttu-id="6b4d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b4d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b4d0-105">收件人表包含有关邮件的所有收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-105">The recipient table contains information about all the recipients for a message.</span></span> <span data-ttu-id="6b4d0-106">邮件存储提供程序实现收件人表，客户端应用程序使用它们。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-106">Message store providers implement recipient tables and client applications use them.</span></span> <span data-ttu-id="6b4d0-107">客户端通过调用 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法或者邮件存储提供程序支持此方法来访问收件人表，从而 [调用 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-107">Clients access a recipient table by making a call to the [IMessage::GetRecipientTable](imessage-getrecipienttable.md) method, or if the message store provider supports it, to the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method.</span></span> <span data-ttu-id="6b4d0-108">客户端使用 **OpenProperty** 访问收件人表，具体方法为PR_MESSAGE_RECIPIENTS (属性标记指定 **)** [PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md) IID_IMAPITable，为接口标识符指定 IID_IMAPITable。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-108">Clients access recipient tables with **OpenProperty** by specifying **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) for the property tag and IID_IMAPITable for the interface identifier.</span></span> <span data-ttu-id="6b4d0-109">可以通过调用 [IMessage：：ModifyRecipients](imessage-modifyrecipients.md) 方法对收件人表进行更改。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-109">Changes to a recipient table can be made by calling the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method.</span></span> 
  
<span data-ttu-id="6b4d0-110">收件人表具有不同的列集，具体取决于是否已提交邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-110">Recipient tables have a different column set depending on whether the message has been submitted.</span></span> <span data-ttu-id="6b4d0-111">下列属性将包含收件人表中所需的列集：</span><span class="sxs-lookup"><span data-stu-id="6b4d0-111">The following properties make up the required column set in recipient tables:</span></span>
  
- <span data-ttu-id="6b4d0-112">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-112">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-113">**PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-113">**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-114">**PR_ROWID (** [PidTagRowid](pidtagrowid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-114">**PR_ROWID** ([PidTagRowid](pidtagrowid-canonical-property.md))</span></span>
    
<span data-ttu-id="6b4d0-115">可选属性包括：</span><span class="sxs-lookup"><span data-stu-id="6b4d0-115">The optional properties are:</span></span>
  
- <span data-ttu-id="6b4d0-116">**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-116">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-117">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-117">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-118">**PR_SPOOLER_STATUS (** [PidTagSpoolerStatus)](pidtagspoolerstatus-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="6b4d0-118">**PR_SPOOLER_STATUS** ([PidTagSpoolerStatus](pidtagspoolerstatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-119">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-119">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
<span data-ttu-id="6b4d0-120">提交的邮件应在所需的列集包含以下附加属性：</span><span class="sxs-lookup"><span data-stu-id="6b4d0-120">Submitted messages should include these additional properties in their required column set:</span></span>
  
- <span data-ttu-id="6b4d0-121">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
- <span data-ttu-id="6b4d0-122">**PR_RESPONSIBILITY (** [PidTagResponsibility](pidtagresponsibility-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="6b4d0-122">**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))</span></span>
    
<span data-ttu-id="6b4d0-123">根据提供程序的实现，其他列（如 **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 和 [ENTRYID）](entryid.md)可能位于表中。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-123">Depending on a provider's implementation, additional columns, such as **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) and [ENTRYID](entryid.md), might be in the table.</span></span>
  
<span data-ttu-id="6b4d0-124">支持邮件传输的任何邮件存储提供程序（如提供程序的 PR_STORE_SUPPORT_MASK ( ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置的 **STORE_SUBMIT_OK** 位所示）都应支持收件人表实现中的一组特定限制。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-124">Any message store provider that supports message transmission — as indicated by the STORE_SUBMIT_OK bit being set in the provider's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property — should offer support for a particular set of restrictions in a recipient table implementation.</span></span> <span data-ttu-id="6b4d0-125">**AND**、 **OR**、 exist 和 属性限制是应该对收件人表用户可用的限制类型之一。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-125">The **AND**, **OR**, exist, and property restrictions are among the types of restrictions that should be available to recipient table users.</span></span> <span data-ttu-id="6b4d0-126">属性限制仅需要支持等于和不等于运算符。</span><span class="sxs-lookup"><span data-stu-id="6b4d0-126">Only the equal and not equal operators need to be supported on the property restriction.</span></span> <span data-ttu-id="6b4d0-127">这些限制必须用于以下属性：</span><span class="sxs-lookup"><span data-stu-id="6b4d0-127">These restrictions must work with the following properties:</span></span>
  
- <span data-ttu-id="6b4d0-128">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="6b4d0-128">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="6b4d0-129">**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="6b4d0-129">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span> 
    
- <span data-ttu-id="6b4d0-130">**PR_RECIPIENT_TYPE**</span><span class="sxs-lookup"><span data-stu-id="6b4d0-130">**PR_RECIPIENT_TYPE**</span></span>
    
- <span data-ttu-id="6b4d0-131">**PR_RESPONSIBILITY**</span><span class="sxs-lookup"><span data-stu-id="6b4d0-131">**PR_RESPONSIBILITY**</span></span>
    
- <span data-ttu-id="6b4d0-132">**PR_SPOOLER_STATUS**</span><span class="sxs-lookup"><span data-stu-id="6b4d0-132">**PR_SPOOLER_STATUS**</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6b4d0-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b4d0-133">See also</span></span>



[<span data-ttu-id="6b4d0-134">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="6b4d0-134">MAPI Tables</span></span>](mapi-tables.md)

