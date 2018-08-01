---
title: 打开消息文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e37fc9d8-433b-41b4-84f2-42a952063f35
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad3499cc1ff3bd8b633fa48173ab8455d5d8d124
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776558"
---
# <a name="opening-message-text"></a><span data-ttu-id="db34a-103">打开消息文本</span><span class="sxs-lookup"><span data-stu-id="db34a-103">Opening message text</span></span>

<span data-ttu-id="db34a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="db34a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="db34a-105">存储的消息的文本中其**PR\_正文**属性或**PR\_RTF\_压缩**属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-105">The text of a message is stored either in its **PR\_BODY** property or **PR\_RTF\_COMPRESSED** property.</span></span> <span data-ttu-id="db34a-106">有关详细信息，请参阅**PR\_正文**([PidTagBody](pidtagbody-canonical-property.md))， **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**PR\_RTF\_压缩**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="db34a-106">For more information, see **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), and **PR\_RTF\_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> 

<span data-ttu-id="db34a-107">如果您支持富文本格式 (RTF)，打开**PR\_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="db34a-107">If you support the Rich Text Format (RTF), open **PR\_RTF_COMPRESSED**.</span></span> <span data-ttu-id="db34a-108">如果您不支持 RTF，打开**PR\_正文**。</span><span class="sxs-lookup"><span data-stu-id="db34a-108">If you do not support RTF, open **PR\_BODY**.</span></span> <span data-ttu-id="db34a-109">由于消息的文本可能很大无论设置格式，使用**IMAPIProp::OpenProperty**打开这些属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-109">Because the text of a message can be large regardless of whether or not it is formatted, use **IMAPIProp::OpenProperty** to open these properties.</span></span> <span data-ttu-id="db34a-110">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="db34a-110">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
  
### <a name="to-display-formatted-message-text"></a><span data-ttu-id="db34a-111">显示带格式的消息文本</span><span class="sxs-lookup"><span data-stu-id="db34a-111">To display formatted message text</span></span>
  
1. <span data-ttu-id="db34a-112">如果您使用的非 RTF 注意消息存储，如缺少 STORE_RTF_OK 标志的存储**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中所示：</span><span class="sxs-lookup"><span data-stu-id="db34a-112">If you are using a non-RTF aware message store, as indicated by the absence of the STORE_RTF_OK flag in the store's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
    
    1. <span data-ttu-id="db34a-113">调用消息的**IMAPIProp::GetProps**方法来检索**PR_RTF_IN_SYNC**属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-113">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_RTF_IN_SYNC** property.</span></span> <span data-ttu-id="db34a-114">有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)和**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="db34a-114">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="db34a-115">调用 RTFSync **PR_RTF_COMPRESSED**属性与同步消息的 PR_BODY 属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-115">Call RTFSync to synchronize the message's PR_BODY property with the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="db34a-116">有关详细信息，请参阅[RTFSync](rtfsync.md)、 **PR_BODY**和**PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="db34a-116">For more information, see [RTFSync](rtfsync.md), **PR_BODY**, and **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="db34a-117">传递 RTF_SYNC_BODY_CHANGED 标记如果调用来检索**PR_RTF_IN_SYNC**失败，因为属性不存在或其设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="db34a-117">Pass the RTF_SYNC_BODY_CHANGED flag if the call to retrieve **PR_RTF_IN_SYNC** failed because the property does not exist or it is set to FALSE.</span></span> 
        
    3. <span data-ttu-id="db34a-118">如果**RTFSync**返回 TRUE — 指示所做更改 — 呼叫消息的**IMAPIProp::SaveChanges**方法永久存储。</span><span class="sxs-lookup"><span data-stu-id="db34a-118">If **RTFSync** returned TRUE — indicating that changes were made — call the message's **IMAPIProp::SaveChanges** method to permanently store them.</span></span> <span data-ttu-id="db34a-119">有关详细信息，请参阅[IMAPIProp::SaveChanges](imapiprop-savechanges.md)。</span><span class="sxs-lookup"><span data-stu-id="db34a-119">For more information, see [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
2. <span data-ttu-id="db34a-120">无论您使用 RTF 感知消息存储：</span><span class="sxs-lookup"><span data-stu-id="db34a-120">Regardless of whether or not you are using an RTF-aware message store:</span></span>
    
    1. <span data-ttu-id="db34a-121">调用**IMAPIProp::OpenProperty**打开**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-121">Call **IMAPIProp::OpenProperty** to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="db34a-122">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="db34a-122">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**.</span></span>
        
    2. <span data-ttu-id="db34a-123">如果**PR_RTF_COMPRESSED**不可用，请调用**OpenProperty**打开**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-123">If **PR_RTF_COMPRESSED** is not available, call **OpenProperty** to open the **PR_BODY** property.</span></span> 
        
    3. <span data-ttu-id="db34a-124">如果可用，请调用**WrapCompressedRTFStream**函数创建的压缩文件的 RTF 数据，未压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="db34a-124">Call the **WrapCompressedRTFStream** function to create an uncompressed version of the compressed RTF data, if available.</span></span> <span data-ttu-id="db34a-125">有关详细信息，请参阅[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。</span><span class="sxs-lookup"><span data-stu-id="db34a-125">For more information, see [WrapCompressedRTFStream](wrapcompressedrtfstream.md).</span></span>
        
    4. <span data-ttu-id="db34a-126">将格式化的文本从流复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="db34a-126">Copy the formatted text from the stream to the appropriate place in the message form.</span></span> 
    
### <a name="to-display-plain-message-text"></a><span data-ttu-id="db34a-127">显示普通消息文本</span><span class="sxs-lookup"><span data-stu-id="db34a-127">To display plain message text</span></span>
  
1. <span data-ttu-id="db34a-128">调用消息的**IMAPIProp::GetProps**方法来检索**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="db34a-128">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_BODY** property.</span></span> <span data-ttu-id="db34a-129">有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="db34a-129">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
2. <span data-ttu-id="db34a-130">如果**GetProps**返回属性值结构或 MAPI_E_NOT_ENOUGH_MEMORY 任一 PT_ERROR 用于属性类型，调用消息的**IMAPIProp::OpenProperty**方法。</span><span class="sxs-lookup"><span data-stu-id="db34a-130">If **GetProps** returns either PT_ERROR for the property type in the property value structure or MAPI_E_NOT_ENOUGH_MEMORY, call the message's **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="db34a-131">作为属性标记和 IID_IStream 接口标识传递**PR_BODY** 。</span><span class="sxs-lookup"><span data-stu-id="db34a-131">Pass **PR_BODY** as the property tag and IID_IStream as the interface identifier.</span></span> <span data-ttu-id="db34a-132">有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="db34a-132">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
3. <span data-ttu-id="db34a-133">将纯文本从流复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="db34a-133">Copy the plain text from the stream to the appropriate place in the message form.</span></span> 
    

