---
title: 以纯文本呈现附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 72b447e9-b4f2-4557-baf5-0afefe463749
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 587736e7ca2f30468b169a33cea34927f857382c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410873"
---
# <a name="rendering-an-attachment-in-plain-text"></a><span data-ttu-id="332e1-103">以纯文本呈现附件</span><span class="sxs-lookup"><span data-stu-id="332e1-103">Rendering an Attachment in Plain Text</span></span>

  
  
<span data-ttu-id="332e1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="332e1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="332e1-105">若要在纯文本邮件中呈现附件，请检索附件的 **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 属性，并应用到 **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性的数据。</span><span class="sxs-lookup"><span data-stu-id="332e1-105">To render an attachment in a message with plain text, retrieve the attachment's **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) property and apply it to the data in the **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) property.</span></span> <span data-ttu-id="332e1-106">有两种方法可以检索 **PR_RENDERING_POSITION：**</span><span class="sxs-lookup"><span data-stu-id="332e1-106">There are two ways to retrieve **PR_RENDERING_POSITION**:</span></span>
  
- <span data-ttu-id="332e1-107">通过调用邮件 **的 IMessage：：OpenAttach** 方法打开附件，然后通过调用附件的 **IMAPIProp：：GetProps** 方法来请求 **PR_RENDERING_POSITION** 属性。</span><span class="sxs-lookup"><span data-stu-id="332e1-107">Open the attachment by calling the message's **IMessage::OpenAttach** method and then ask for the **PR_RENDERING_POSITION** property by calling the attachment's **IMAPIProp::GetProps** method.</span></span> <span data-ttu-id="332e1-108">有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md) 和 [IMAPIProp：：GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="332e1-108">For more information, see [IMessage::OpenAttach](imessage-openattach.md) and [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
- <span data-ttu-id="332e1-109">调用邮件的 **IMessage：：GetAttachmentTable** 方法以访问其附件表并检索包含 **PR_RENDERING_POSITION** 属性的列。</span><span class="sxs-lookup"><span data-stu-id="332e1-109">Call the message's **IMessage::GetAttachmentTable** method to access its attachment table and retrieve the column that holds the **PR_RENDERING_POSITION** property.</span></span> <span data-ttu-id="332e1-110">这种方法始终更可取。</span><span class="sxs-lookup"><span data-stu-id="332e1-110">This way is always preferable.</span></span> <span data-ttu-id="332e1-111">有关详细信息，请参阅 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md)。</span><span class="sxs-lookup"><span data-stu-id="332e1-111">For more information, see [IMessage::GetAttachmentTable](imessage-getattachmenttable.md).</span></span>
    
<span data-ttu-id="332e1-112">请记住，许多 RTF 感知邮件存储不会计算PR_RENDERING_POSITION直到客户端请求邮件的 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="332e1-112">Keep in mind that many RTF-aware message stores do not calculate **PR_RENDERING_POSITION** until a client requests the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property of a message.</span></span> <span data-ttu-id="332e1-113">在此之前 **，PR_RENDERING_POSITION通常** 表示一个近似值。</span><span class="sxs-lookup"><span data-stu-id="332e1-113">Until that time, **PR_RENDERING_POSITION** usually represents an approximate value.</span></span> <span data-ttu-id="332e1-114">允许邮件存储提供程序向客户端提供近似值以提高性能。</span><span class="sxs-lookup"><span data-stu-id="332e1-114">Message store providers are allowed to supply clients with an approximate value to enhance performance.</span></span> 
  
<span data-ttu-id="332e1-115">文件或二进制附件的呈现存储在其 **PR_ATTACH_RENDERING** 属性中。</span><span class="sxs-lookup"><span data-stu-id="332e1-115">The rendering for a file or binary attachment is stored in its **PR_ATTACH_RENDERING** property.</span></span> <span data-ttu-id="332e1-116">可以选择使用与检索 PR_ATTACH_RENDERING相同的方法检索 **PR_RENDERING_POSITION：直接从** 附件或附件表中检索。</span><span class="sxs-lookup"><span data-stu-id="332e1-116">You have the choice of retrieving **PR_ATTACH_RENDERING** in the same ways as you retrieved **PR_RENDERING_POSITION**: directly from the attachment or from the attachment table.</span></span> <span data-ttu-id="332e1-117">对于 **PR_ATTACH_RENDERING，** 第一个策略虽然比较耗时，但更安全。</span><span class="sxs-lookup"><span data-stu-id="332e1-117">For **PR_ATTACH_RENDERING**, the first strategy, although more time-consuming, is safer.</span></span> <span data-ttu-id="332e1-118">由于某些邮件存储提供程序将表列截断为 255 字节，或在某些情况下为 510 字节，因此很难确定 **PR_ATTACH_RENDERING** 列包含完整呈现。</span><span class="sxs-lookup"><span data-stu-id="332e1-118">Because some message store providers truncate their table columns to 255 bytes, or in a few cases 510 bytes, it is difficult to be sure that the **PR_ATTACH_RENDERING** column contains the complete rendering.</span></span> <span data-ttu-id="332e1-119">当直接从附件检索属性时，它将始终完整。</span><span class="sxs-lookup"><span data-stu-id="332e1-119">When retrieving the property directly from the attachment, it will always be complete.</span></span> 
  
<span data-ttu-id="332e1-120">OLE 和邮件附件均未 **PR_ATTACH_RENDERING。**</span><span class="sxs-lookup"><span data-stu-id="332e1-120">Neither OLE nor message attachments set **PR_ATTACH_RENDERING**.</span></span> <span data-ttu-id="332e1-121">相反，OLE 1 附件的呈现信息存储在邮件文本流中。</span><span class="sxs-lookup"><span data-stu-id="332e1-121">Instead, rendering information for OLE 1 attachments is stored in the message text stream.</span></span> <span data-ttu-id="332e1-122">对于 OLE 2 附件，它存储在存储对象的特殊子流中。</span><span class="sxs-lookup"><span data-stu-id="332e1-122">For OLE 2 attachments, it is stored in a special child stream of the storage object.</span></span> <span data-ttu-id="332e1-123">邮件附件的呈现信息通过表单管理器提供。</span><span class="sxs-lookup"><span data-stu-id="332e1-123">Rendering information for message attachments is available through the form manager.</span></span> 
  
 <span data-ttu-id="332e1-124">**检索邮件附件的呈现**</span><span class="sxs-lookup"><span data-stu-id="332e1-124">**To retrieve the rendering for a message attachment**</span></span>
  
1. <span data-ttu-id="332e1-125">使用邮件的邮件类访问表单管理器。</span><span class="sxs-lookup"><span data-stu-id="332e1-125">Use the message class of the message to access the form manager.</span></span>
    
2. <span data-ttu-id="332e1-126">访问表单管理器的 **PR_MINI_ICON** 属性。</span><span class="sxs-lookup"><span data-stu-id="332e1-126">Access the form manager's **PR_MINI_ICON** property.</span></span> <span data-ttu-id="332e1-127">有关详细信息，请参阅 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="332e1-127">For more information, see **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)).</span></span>
    

