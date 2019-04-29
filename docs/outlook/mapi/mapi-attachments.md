---
title: MAPI 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e6c6ad9-1e07-4234-a5ef-18020d7ce468
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 90fbec8b61499f383228823d69b041a21199a22e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417831"
---
# <a name="mapi-attachments"></a><span data-ttu-id="1ea14-103">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="1ea14-103">MAPI Attachments</span></span>

  
  
<span data-ttu-id="1ea14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ea14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ea14-105">某些邮件存储提供程序使客户端能够将文件、OLE 对象、消息或二进制数据的格式添加的信息与邮件相关联。</span><span class="sxs-lookup"><span data-stu-id="1ea14-105">Some message store providers enable clients to associate added information in the form of files, OLE objects, messages, or binary data with messages.</span></span> <span data-ttu-id="1ea14-106">此添加的信息称为邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="1ea14-106">This added information is called a message's attachment.</span></span> <span data-ttu-id="1ea14-107">由于附件是通过其邮件进行创建、维护和访问的, 因此它们被视为邮件子消息。</span><span class="sxs-lookup"><span data-stu-id="1ea14-107">Because attachments are created, maintained, and accessed only through their messages, they are considered message subobjects.</span></span> <span data-ttu-id="1ea14-108">附件具有称为附件编号的连续号码, 而不是访问的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1ea14-108">Rather than having an entry identifier for access, attachments have a sequential number known as an attachment number.</span></span> <span data-ttu-id="1ea14-109">此数字唯一标识其邮件中的附件, 但不一定是邮件存储区中的附件。</span><span class="sxs-lookup"><span data-stu-id="1ea14-109">This number uniquely identifies the attachment within its message, but not necessarily within the message store.</span></span> <span data-ttu-id="1ea14-110">两个不同的邮件可以具有具有相同附件编号的不同附件。</span><span class="sxs-lookup"><span data-stu-id="1ea14-110">Two different messages can have different attachments with the same attachment number.</span></span> <span data-ttu-id="1ea14-111">附件编号仅在邮件打开并存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中时才有效。</span><span class="sxs-lookup"><span data-stu-id="1ea14-111">Attachment numbers are only valid as long as the message is open and are stored in the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="1ea14-112">若要访问有关邮件所有附件的摘要信息, 客户端将检索其附件表。</span><span class="sxs-lookup"><span data-stu-id="1ea14-112">To access summary information about all of a message's attachments, clients retrieve its attachment table.</span></span> <span data-ttu-id="1ea14-113">附件表包含客户端可直接访问附件的信息, 如附件编号和记录密钥。</span><span class="sxs-lookup"><span data-stu-id="1ea14-113">The attachment table includes information that clients can use to access an attachment directly, such as its attachment number and record key.</span></span> <span data-ttu-id="1ea14-114">客户端可以通过以下方式检索附件表:</span><span class="sxs-lookup"><span data-stu-id="1ea14-114">Clients can retrieve an attachment table by:</span></span>
  
- <span data-ttu-id="1ea14-115">调用**IMessage:: GetAttachmentTable**。</span><span class="sxs-lookup"><span data-stu-id="1ea14-115">Calling **IMessage::GetAttachmentTable**.</span></span> <span data-ttu-id="1ea14-116">有关详细信息, 请参阅[IMessage:: GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea14-116">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
- <span data-ttu-id="1ea14-117">调用**IMAPIProp:: OpenProperty**。</span><span class="sxs-lookup"><span data-stu-id="1ea14-117">Calling **IMAPIProp::OpenProperty**.</span></span> <span data-ttu-id="1ea14-118">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea14-118">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="1ea14-119">邮件存储提供程序应支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="1ea14-119">Message store providers are expected to support both of these approaches.</span></span> <span data-ttu-id="1ea14-120">**OpenProperty**方法要求调用方将 IID_IMAPITable 指定为接口标识符, 并将**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 指定为属性标记。</span><span class="sxs-lookup"><span data-stu-id="1ea14-120">The **OpenProperty** approach requires that the caller specify IID_IMAPITable as the interface identifier and **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) as the property tag.</span></span> <span data-ttu-id="1ea14-121">**PR_MESSAGE_ATTACHMENTS**是一个 table 对象属性, 该对象代表邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="1ea14-121">**PR_MESSAGE_ATTACHMENTS** is a table object property that represents a message's attachment table.</span></span> <span data-ttu-id="1ea14-122">邮件存储提供程序需要设置每个邮件的**PR_MESSAGE_ATTACHMENTS** , 并将其包含在从**IMAPIProp:: GetPropList**方法返回的属性标记数组中。</span><span class="sxs-lookup"><span data-stu-id="1ea14-122">Message store providers are required to set **PR_MESSAGE_ATTACHMENTS** for each message and include it in the array of property tags returned from the **IMAPIProp::GetPropList** method.</span></span> <span data-ttu-id="1ea14-123">有关详细信息, 请参阅[IMAPIProp:: GetPropList](imapiprop-getproplist.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea14-123">For more information, see [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span>
  
 <span data-ttu-id="1ea14-124">可以使用**PR_MESSAGE_ATTACHMENTS** :</span><span class="sxs-lookup"><span data-stu-id="1ea14-124">**PR_MESSAGE_ATTACHMENTS** can be used:</span></span> 
  
- <span data-ttu-id="1ea14-125">使用**IMAPIProp:: OpenProperty**访问附件或收件人表。</span><span class="sxs-lookup"><span data-stu-id="1ea14-125">With **IMAPIProp::OpenProperty** to access an attachment or recipient table.</span></span> 
    
- <span data-ttu-id="1ea14-126">使用**IMAPIProp:: CopyTo**或**IMAPIProp:: CopyProps**在复制时排除或包含附件。</span><span class="sxs-lookup"><span data-stu-id="1ea14-126">With **IMAPIProp::CopyTo** or **IMAPIProp::CopyProps** to exclude or include attachments when copying.</span></span> <span data-ttu-id="1ea14-127">有关详细信息, 请参阅[IMAPIProp:: CopyTo](imapiprop-copyto.md) and [IMAPIProp:: CopyProps](imapiprop-copyprops.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea14-127">For more information, see [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md).</span></span>
    
- <span data-ttu-id="1ea14-128">在子元素限制中, 指示应将子限制应用于附件。</span><span class="sxs-lookup"><span data-stu-id="1ea14-128">In a subobject restriction to indicate that the child restriction should apply to attachments.</span></span>
    
<span data-ttu-id="1ea14-129">有关详细信息, 请参阅[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1ea14-129">For more information, see [Attachment Tables](attachment-tables.md).</span></span>
  

