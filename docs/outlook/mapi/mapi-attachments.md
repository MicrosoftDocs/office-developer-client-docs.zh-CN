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
# <a name="mapi-attachments"></a><span data-ttu-id="525db-103">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="525db-103">MAPI Attachments</span></span>

  
  
<span data-ttu-id="525db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="525db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="525db-105">某些邮件存储提供程序使客户端可以将添加的信息以文件、OLE 对象、邮件或二进制数据的形式与邮件关联。</span><span class="sxs-lookup"><span data-stu-id="525db-105">Some message store providers enable clients to associate added information in the form of files, OLE objects, messages, or binary data with messages.</span></span> <span data-ttu-id="525db-106">此添加的信息称为邮件附件。</span><span class="sxs-lookup"><span data-stu-id="525db-106">This added information is called a message's attachment.</span></span> <span data-ttu-id="525db-107">由于附件仅通过邮件创建、维护和访问，因此被视为邮件子对象。</span><span class="sxs-lookup"><span data-stu-id="525db-107">Because attachments are created, maintained, and accessed only through their messages, they are considered message subobjects.</span></span> <span data-ttu-id="525db-108">附件具有一个称为附件编号的顺序编号，而不是具有用于访问的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="525db-108">Rather than having an entry identifier for access, attachments have a sequential number known as an attachment number.</span></span> <span data-ttu-id="525db-109">此编号唯一标识邮件中的附件，但不一定是邮件存储中的附件。</span><span class="sxs-lookup"><span data-stu-id="525db-109">This number uniquely identifies the attachment within its message, but not necessarily within the message store.</span></span> <span data-ttu-id="525db-110">两个不同的邮件可以具有相同的附件号的不同附件。</span><span class="sxs-lookup"><span data-stu-id="525db-110">Two different messages can have different attachments with the same attachment number.</span></span> <span data-ttu-id="525db-111">只有邮件已打开且存储在[PidTagAttachNumber](pidtagattachnumber-canonical-property.md) PR_ATTACH_NUM (中，附件) 有效。</span><span class="sxs-lookup"><span data-stu-id="525db-111">Attachment numbers are only valid as long as the message is open and are stored in the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="525db-112">若要访问有关邮件的所有附件的摘要信息，客户端将检索其附件表。</span><span class="sxs-lookup"><span data-stu-id="525db-112">To access summary information about all of a message's attachments, clients retrieve its attachment table.</span></span> <span data-ttu-id="525db-113">附件表包含客户端可用于直接访问附件的信息，例如附件编号和记录密钥。</span><span class="sxs-lookup"><span data-stu-id="525db-113">The attachment table includes information that clients can use to access an attachment directly, such as its attachment number and record key.</span></span> <span data-ttu-id="525db-114">客户端可以检索附件表，方法为：</span><span class="sxs-lookup"><span data-stu-id="525db-114">Clients can retrieve an attachment table by:</span></span>
  
- <span data-ttu-id="525db-115">调用 **IMessage：：GetAttachmentTable**。</span><span class="sxs-lookup"><span data-stu-id="525db-115">Calling **IMessage::GetAttachmentTable**.</span></span> <span data-ttu-id="525db-116">有关详细信息，请参阅 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="525db-116">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
- <span data-ttu-id="525db-117">调用 **IMAPIProp：：OpenProperty**。</span><span class="sxs-lookup"><span data-stu-id="525db-117">Calling **IMAPIProp::OpenProperty**.</span></span> <span data-ttu-id="525db-118">有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="525db-118">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
<span data-ttu-id="525db-119">邮件存储提供程序应支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="525db-119">Message store providers are expected to support both of these approaches.</span></span> <span data-ttu-id="525db-120">**OpenProperty** 方法要求调用方将 IID_IMAPITable 指定为接口标识符，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性标记。 </span><span class="sxs-lookup"><span data-stu-id="525db-120">The **OpenProperty** approach requires that the caller specify IID_IMAPITable as the interface identifier and **PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) as the property tag.</span></span> <span data-ttu-id="525db-121">**PR_MESSAGE_ATTACHMENTS** 是一个 table 对象属性，表示邮件的附件表。</span><span class="sxs-lookup"><span data-stu-id="525db-121">**PR_MESSAGE_ATTACHMENTS** is a table object property that represents a message's attachment table.</span></span> <span data-ttu-id="525db-122">邮件存储提供程序需要为PR_MESSAGE_ATTACHMENTS设置值，并包括到 **从 IMAPIProp：：GetPropList** 方法返回的属性标记数组中。</span><span class="sxs-lookup"><span data-stu-id="525db-122">Message store providers are required to set **PR_MESSAGE_ATTACHMENTS** for each message and include it in the array of property tags returned from the **IMAPIProp::GetPropList** method.</span></span> <span data-ttu-id="525db-123">有关详细信息，请参阅 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)。</span><span class="sxs-lookup"><span data-stu-id="525db-123">For more information, see [IMAPIProp::GetPropList](imapiprop-getproplist.md).</span></span>
  
 <span data-ttu-id="525db-124">**PR_MESSAGE_ATTACHMENTS** 可以使用：</span><span class="sxs-lookup"><span data-stu-id="525db-124">**PR_MESSAGE_ATTACHMENTS** can be used:</span></span> 
  
- <span data-ttu-id="525db-125">使用 **IMAPIProp：：OpenProperty** 访问附件或收件人表。</span><span class="sxs-lookup"><span data-stu-id="525db-125">With **IMAPIProp::OpenProperty** to access an attachment or recipient table.</span></span> 
    
- <span data-ttu-id="525db-126">使用 **IMAPIProp：：CopyTo** 或 **IMAPIProp：：CopyProps** 在复制时排除或包括附件。</span><span class="sxs-lookup"><span data-stu-id="525db-126">With **IMAPIProp::CopyTo** or **IMAPIProp::CopyProps** to exclude or include attachments when copying.</span></span> <span data-ttu-id="525db-127">有关详细信息，请参阅 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 和 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。</span><span class="sxs-lookup"><span data-stu-id="525db-127">For more information, see [IMAPIProp::CopyTo](imapiprop-copyto.md) and [IMAPIProp::CopyProps](imapiprop-copyprops.md).</span></span>
    
- <span data-ttu-id="525db-128">在子对象限制中，指示子限制应应用于附件。</span><span class="sxs-lookup"><span data-stu-id="525db-128">In a subobject restriction to indicate that the child restriction should apply to attachments.</span></span>
    
<span data-ttu-id="525db-129">有关详细信息，请参阅附件 [表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="525db-129">For more information, see [Attachment Tables](attachment-tables.md).</span></span>
  

