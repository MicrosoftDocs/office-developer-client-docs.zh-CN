---
title: MAPI 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e6c6ad9-1e07-4234-a5ef-18020d7ce468
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c6538f8fef7d8ccb87b6e6d9d2b9c68779ca8582
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776203"
---
# <a name="mapi-attachments"></a><span data-ttu-id="6b4f4-103">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="6b4f4-103">MAPI Attachments</span></span>

  
  
<span data-ttu-id="6b4f4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6b4f4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6b4f4-105">某些消息存储提供程序使客户端与邮件相关联的文件、 OLE 对象、 邮件或二进制数据形式添加了的信息。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-105">Some message store providers enable clients to associate added information in the form of files, OLE objects, messages, or binary data with messages.</span></span> <span data-ttu-id="6b4f4-106">此添加了的信息称为邮件附件。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-106">This added information is called a message's attachment.</span></span> <span data-ttu-id="6b4f4-107">附件是创建、 维护和只能通过其邮件访问，因为它们被视为消息子对象。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-107">Because attachments are created, maintained, and accessed only through their messages, they are considered message subobjects.</span></span> <span data-ttu-id="6b4f4-108">而不是具有访问的项标识符，附件具有附件编号的顺序的数字已知。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-108">Rather than having an entry identifier for access, attachments have a sequential number known as an attachment number.</span></span> <span data-ttu-id="6b4f4-109">此号码唯一标识在其消息中，但不是一定的消息存储中的附件。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-109">This number uniquely identifies the attachment within its message, but not necessarily within the message store.</span></span> <span data-ttu-id="6b4f4-110">两个不同的消息可以具有不同附件具有相同的附件编号。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-110">Two different messages can have different attachments with the same attachment number.</span></span> <span data-ttu-id="6b4f4-111">只要邮件处于打开状态，并存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，附件号码才有效。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-111">Attachment numbers are only valid as long as the message is open and are stored in the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="6b4f4-112">若要访问所有邮件的附件的摘要信息，客户端检索其附件表。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-112">To access summary information about all of a message's attachments, clients retrieve its attachment table.</span></span> <span data-ttu-id="6b4f4-113">附件表包含客户端可以使用直接访问附件，例如其附件编号和记录的键的信息。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-113">The attachment table includes information that clients can use to access an attachment directly, such as its attachment number and record key.</span></span> <span data-ttu-id="6b4f4-114">客户端可取回附件的表：</span><span class="sxs-lookup"><span data-stu-id="6b4f4-114">Clients can retrieve an attachment table by:</span></span>
  
- <span data-ttu-id="6b4f4-115">调用**IMessage::GetAttachmentTable**。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-115">Calling **IMessage::GetAttachmentTable**.</span></span> <span data-ttu-id="6b4f4-116">有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-116">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
- <span data-ttu-id="6b4f4-117">调用**IMAPIProp::OpenProperty**。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-117">Calling **IMAPIProp::OpenProperty**.</span></span> <span data-ttu-id="6b4f4-118">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-118">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="6b4f4-119">消息存储提供程序需要支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-119">Message store providers are expected to support both of these approaches.</span></span> <span data-ttu-id="6b4f4-120">**OpenProperty**方法需要呼叫者指定为接口标识符和**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) IID_IMAPITable 属性标记为。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-120">The **OpenProperty** approach requires that the caller specify IID_IMAPITable as the interface identifier and **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) as the property tag.</span></span> <span data-ttu-id="6b4f4-121">**PR_MESSAGE_ATTACHMENTS**是一个表示一条消息的附件表的表对象属性。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-121">**PR_MESSAGE_ATTACHMENTS** is a table object property that represents a message's attachment table.</span></span> <span data-ttu-id="6b4f4-122">消息存储提供程序所需设置**PR_MESSAGE_ATTACHMENTS**关于每封邮件，并将其加入属性标记从**IMAPIProp::GetPropList**方法返回的数组。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-122">Message store providers are required to set **PR_MESSAGE_ATTACHMENTS** for each message and include it in the array of property tags returned from the **IMAPIProp::GetPropList** method.</span></span> <span data-ttu-id="6b4f4-123">有关详细信息，请参阅[IMAPIProp::GetPropList](imapiprop-getproplist.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-123">For more information, see [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span>
  
 <span data-ttu-id="6b4f4-124">可以使用**PR_MESSAGE_ATTACHMENTS** :</span><span class="sxs-lookup"><span data-stu-id="6b4f4-124">**PR_MESSAGE_ATTACHMENTS** can be used:</span></span> 
  
- <span data-ttu-id="6b4f4-125">与**IMAPIProp::OpenProperty**访问附件或收件人的表。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-125">With **IMAPIProp::OpenProperty** to access an attachment or recipient table.</span></span> 
    
- <span data-ttu-id="6b4f4-126">与**IMAPIProp::CopyTo**或**IMAPIProp::CopyProps**排除或包括附件时复制。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-126">With **IMAPIProp::CopyTo** or **IMAPIProp::CopyProps** to exclude or include attachments when copying.</span></span> <span data-ttu-id="6b4f4-127">有关详细信息，请参阅[IMAPIProp::CopyTo](imapiprop-copyto.md)和[IMAPIProp::CopyProps](imapiprop-copyprops.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-127">For more information, see [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md).</span></span>
    
- <span data-ttu-id="6b4f4-128">在以指明子限制应该应用到的附件的子对象限制。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-128">In a subobject restriction to indicate that the child restriction should apply to attachments.</span></span>
    
<span data-ttu-id="6b4f4-129">有关详细信息，请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="6b4f4-129">For more information, see [Attachment Tables](attachment-tables.md).</span></span>
  

