---
title: 以纯文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72b447e9-b4f2-4557-baf5-0afefe463749
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 031f8f17ae98bd62043a2cd8ce6c8c2d55a19c9f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582334"
---
# <a name="rendering-an-attachment-in-plain-text"></a><span data-ttu-id="4f138-103">以纯文本呈现附件</span><span class="sxs-lookup"><span data-stu-id="4f138-103">Rendering an Attachment in Plain Text</span></span>

  
  
<span data-ttu-id="4f138-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4f138-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4f138-105">若要呈现与纯文本邮件的附件，检索附件的**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性，并将其应用到**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 中的数据属性。</span><span class="sxs-lookup"><span data-stu-id="4f138-105">To render an attachment in a message with plain text, retrieve the attachment's **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property and apply it to the data in the **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) property.</span></span> <span data-ttu-id="4f138-106">有两种方法来检索**PR_RENDERING_POSITION**:</span><span class="sxs-lookup"><span data-stu-id="4f138-106">There are two ways to retrieve **PR_RENDERING_POSITION**:</span></span>
  
- <span data-ttu-id="4f138-107">通过调用消息的**IMessage::OpenAttach**方法打开附件，并通过调用附件的**IMAPIProp::GetProps**方法询问**PR_RENDERING_POSITION**属性。</span><span class="sxs-lookup"><span data-stu-id="4f138-107">Open the attachment by calling the message's **IMessage::OpenAttach** method and then ask for the **PR_RENDERING_POSITION** property by calling the attachment's **IMAPIProp::GetProps** method.</span></span> <span data-ttu-id="4f138-108">有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)和[IMAPIProp::GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="4f138-108">For more information, see [IMessage::OpenAttach](imessage-openattach.md) and [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
- <span data-ttu-id="4f138-109">调用消息的**IMessage::GetAttachmentTable**方法访问其附件表并检索包含**PR_RENDERING_POSITION**属性的列。</span><span class="sxs-lookup"><span data-stu-id="4f138-109">Call the message's **IMessage::GetAttachmentTable** method to access its attachment table and retrieve the column that holds the **PR_RENDERING_POSITION** property.</span></span> <span data-ttu-id="4f138-110">这种方式始终是最好的。</span><span class="sxs-lookup"><span data-stu-id="4f138-110">This way is always preferable.</span></span> <span data-ttu-id="4f138-111">有关详细信息，请参阅[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="4f138-111">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
<span data-ttu-id="4f138-112">请记住，许多 RTF 感知的消息存储不计算**PR_RENDERING_POSITION**直到客户端请求一条消息的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4f138-112">Keep in mind that many RTF-aware message stores do not calculate **PR_RENDERING_POSITION** until a client requests the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property of a message.</span></span> <span data-ttu-id="4f138-113">之前， **PR_RENDERING_POSITION**通常表示估计值。</span><span class="sxs-lookup"><span data-stu-id="4f138-113">Until that time, **PR_RENDERING_POSITION** usually represents an approximate value.</span></span> <span data-ttu-id="4f138-114">消息存储提供程序允许客户端提供估计值以提高性能。</span><span class="sxs-lookup"><span data-stu-id="4f138-114">Message store providers are allowed to supply clients with an approximate value to enhance performance.</span></span> 
  
<span data-ttu-id="4f138-115">文件或二进制附件呈现存储在其**PR_ATTACH_RENDERING**属性中。</span><span class="sxs-lookup"><span data-stu-id="4f138-115">The rendering for a file or binary attachment is stored in its **PR_ATTACH_RENDERING** property.</span></span> <span data-ttu-id="4f138-116">您可以选择的相同方式检索**PR_ATTACH_RENDERING** ，如检索**PR_RENDERING_POSITION**： 直接从附件或附件表。</span><span class="sxs-lookup"><span data-stu-id="4f138-116">You have the choice of retrieving **PR_ATTACH_RENDERING** in the same ways as you retrieved **PR_RENDERING_POSITION**: directly from the attachment or from the attachment table.</span></span> <span data-ttu-id="4f138-117">为**PR_ATTACH_RENDERING**，第一种策略，尽管更加耗时，更安全。</span><span class="sxs-lookup"><span data-stu-id="4f138-117">For **PR_ATTACH_RENDERING**, the first strategy, although more time-consuming, is safer.</span></span> <span data-ttu-id="4f138-118">由于某些消息存储提供程序截断为 255 个字节，或在少数情况下 510 字节其表格列，因此很难以确保**PR_ATTACH_RENDERING**列中包含完整的呈现。</span><span class="sxs-lookup"><span data-stu-id="4f138-118">Because some message store providers truncate their table columns to 255 bytes, or in a few cases 510 bytes, it is difficult to be sure that the **PR_ATTACH_RENDERING** column contains the complete rendering.</span></span> <span data-ttu-id="4f138-119">直接从附件中检索属性时，它始终将完成。</span><span class="sxs-lookup"><span data-stu-id="4f138-119">When retrieving the property directly from the attachment, it will always be complete.</span></span> 
  
<span data-ttu-id="4f138-120">OLE 和消息都不附件设置**PR_ATTACH_RENDERING**。</span><span class="sxs-lookup"><span data-stu-id="4f138-120">Neither OLE nor message attachments set **PR_ATTACH_RENDERING**.</span></span> <span data-ttu-id="4f138-121">而是 OLE 1 附件的呈现信息存储在消息文本流。</span><span class="sxs-lookup"><span data-stu-id="4f138-121">Instead, rendering information for OLE 1 attachments is stored in the message text stream.</span></span> <span data-ttu-id="4f138-122">对于 OLE 2 的附件，它存储在存储对象的特殊子流。</span><span class="sxs-lookup"><span data-stu-id="4f138-122">For OLE 2 attachments, it is stored in a special child stream of the storage object.</span></span> <span data-ttu-id="4f138-123">呈现邮件附件信息是可通过窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="4f138-123">Rendering information for message attachments is available through the form manager.</span></span> 
  
 <span data-ttu-id="4f138-124">**若要检索的邮件附件的呈现**</span><span class="sxs-lookup"><span data-stu-id="4f138-124">**To retrieve the rendering for a message attachment**</span></span>
  
1. <span data-ttu-id="4f138-125">使用邮件的邮件类访问窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="4f138-125">Use the message class of the message to access the form manager.</span></span>
    
2. <span data-ttu-id="4f138-126">访问表单经理**PR_MINI_ICON**属性。</span><span class="sxs-lookup"><span data-stu-id="4f138-126">Access the form manager's **PR_MINI_ICON** property.</span></span> <span data-ttu-id="4f138-127">有关详细信息，请参阅**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="4f138-127">For more information, see **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)).</span></span>
    

