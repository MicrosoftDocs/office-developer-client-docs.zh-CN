---
title: 打开邮件文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e37fc9d8-433b-41b4-84f2-42a952063f35
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 305b0534f828ea72c1e116fd38fb8f578062e32e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348578"
---
# <a name="opening-message-text"></a><span data-ttu-id="289fc-103">打开邮件文本</span><span class="sxs-lookup"><span data-stu-id="289fc-103">Opening message text</span></span>

<span data-ttu-id="289fc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="289fc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="289fc-105">邮件的文本存储在其 " **pr\_正文**" 属性或 " **\_pr RTF\_" 压缩**属性中。</span><span class="sxs-lookup"><span data-stu-id="289fc-105">The text of a message is stored either in its **PR\_BODY** property or **PR\_RTF\_COMPRESSED** property.</span></span> <span data-ttu-id="289fc-106">有关详细信息, 请**参阅\_pr 正文**([PidTagBody](pidtagbody-canonical-property.md)) **、\_pr HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和**pr\_RTF\_压缩**([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="289fc-106">For more information, see **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), and **PR\_RTF\_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> 

<span data-ttu-id="289fc-107">如果你支持 rtf 格式 (rtf), 请打开 " **PR\_RTF_COMPRESSED**"。</span><span class="sxs-lookup"><span data-stu-id="289fc-107">If you support the Rich Text Format (RTF), open **PR\_RTF_COMPRESSED**.</span></span> <span data-ttu-id="289fc-108">如果您不支持 RTF, 请打开 **"\_PR 正文**"。</span><span class="sxs-lookup"><span data-stu-id="289fc-108">If you do not support RTF, open **PR\_BODY**.</span></span> <span data-ttu-id="289fc-109">由于邮件的文本可能会很大而不管是否已对其进行格式设置, 因此请使用**IMAPIProp:: OpenProperty**打开这些属性。</span><span class="sxs-lookup"><span data-stu-id="289fc-109">Because the text of a message can be large regardless of whether or not it is formatted, use **IMAPIProp::OpenProperty** to open these properties.</span></span> <span data-ttu-id="289fc-110">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="289fc-110">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
  
### <a name="to-display-formatted-message-text"></a><span data-ttu-id="289fc-111">显示已设置格式的邮件文本</span><span class="sxs-lookup"><span data-stu-id="289fc-111">To display formatted message text</span></span>
  
1. <span data-ttu-id="289fc-112">如果您使用的是非 RTF 感知邮件存储, 则在 store 的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中缺少 STORE_RTF_OK 标志时表示:</span><span class="sxs-lookup"><span data-stu-id="289fc-112">If you are using a non-RTF aware message store, as indicated by the absence of the STORE_RTF_OK flag in the store's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
    
    1. <span data-ttu-id="289fc-113">调用邮件的**IMAPIProp:: GetProps**方法以检索**PR_RTF_IN_SYNC**属性。</span><span class="sxs-lookup"><span data-stu-id="289fc-113">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_RTF_IN_SYNC** property.</span></span> <span data-ttu-id="289fc-114">有关详细信息, 请参阅[IMAPIProp:: GetProps](imapiprop-getprops.md) and **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="289fc-114">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="289fc-115">调用 RTFSync 以将邮件的 PR_BODY 属性与**PR_RTF_COMPRESSED**属性同步。</span><span class="sxs-lookup"><span data-stu-id="289fc-115">Call RTFSync to synchronize the message's PR_BODY property with the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="289fc-116">有关详细信息, 请参阅[RTFSync](rtfsync.md)、 **PR_BODY**和**PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="289fc-116">For more information, see [RTFSync](rtfsync.md), **PR_BODY**, and **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="289fc-117">如果由于属性不存在或设置为 FALSE, 则对检索**PR_RTF_IN_SYNC**的调用失败时传递 RTF_SYNC_BODY_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="289fc-117">Pass the RTF_SYNC_BODY_CHANGED flag if the call to retrieve **PR_RTF_IN_SYNC** failed because the property does not exist or it is set to FALSE.</span></span> 
        
    3. <span data-ttu-id="289fc-118">如果**RTFSync**返回 TRUE (指示所做的更改), 则调用邮件的**IMAPIProp:: SaveChanges**方法以永久存储它们。</span><span class="sxs-lookup"><span data-stu-id="289fc-118">If **RTFSync** returned TRUE — indicating that changes were made — call the message's **IMAPIProp::SaveChanges** method to permanently store them.</span></span> <span data-ttu-id="289fc-119">有关详细信息, 请参阅[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)。</span><span class="sxs-lookup"><span data-stu-id="289fc-119">For more information, see [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
2. <span data-ttu-id="289fc-120">无论您是否使用的是 RTF 感知邮件存储区:</span><span class="sxs-lookup"><span data-stu-id="289fc-120">Regardless of whether or not you are using an RTF-aware message store:</span></span>
    
    1. <span data-ttu-id="289fc-121">调用**IMAPIProp:: OpenProperty**以打开**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="289fc-121">Call **IMAPIProp::OpenProperty** to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="289fc-122">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="289fc-122">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**.</span></span>
        
    2. <span data-ttu-id="289fc-123">如果**PR_RTF_COMPRESSED**不可用, 则调用**OpenProperty**以打开**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="289fc-123">If **PR_RTF_COMPRESSED** is not available, call **OpenProperty** to open the **PR_BODY** property.</span></span> 
        
    3. <span data-ttu-id="289fc-124">调用**WrapCompressedRTFStream**函数以创建压缩的 RTF 数据的未压缩版本 (如果可用)。</span><span class="sxs-lookup"><span data-stu-id="289fc-124">Call the **WrapCompressedRTFStream** function to create an uncompressed version of the compressed RTF data, if available.</span></span> <span data-ttu-id="289fc-125">有关详细信息, 请参阅[WrapCompressedRTFStream](wrapcompressedrtfstream.md)。</span><span class="sxs-lookup"><span data-stu-id="289fc-125">For more information, see [WrapCompressedRTFStream](wrapcompressedrtfstream.md).</span></span>
        
    4. <span data-ttu-id="289fc-126">将格式文本从流中复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="289fc-126">Copy the formatted text from the stream to the appropriate place in the message form.</span></span> 
    
### <a name="to-display-plain-message-text"></a><span data-ttu-id="289fc-127">显示纯文本消息文本</span><span class="sxs-lookup"><span data-stu-id="289fc-127">To display plain message text</span></span>
  
1. <span data-ttu-id="289fc-128">调用邮件的**IMAPIProp:: GetProps**方法以检索**PR_BODY**属性。</span><span class="sxs-lookup"><span data-stu-id="289fc-128">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_BODY** property.</span></span> <span data-ttu-id="289fc-129">有关详细信息, 请参阅[IMAPIProp:: GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="289fc-129">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
2. <span data-ttu-id="289fc-130">如果**GetProps**返回属性值结构或 MAPI_E_NOT_ENOUGH_MEMORY 中的属性类型的 PT_ERROR, 请调用邮件的**IMAPIProp:: OpenProperty**方法。</span><span class="sxs-lookup"><span data-stu-id="289fc-130">If **GetProps** returns either PT_ERROR for the property type in the property value structure or MAPI_E_NOT_ENOUGH_MEMORY, call the message's **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="289fc-131">将**PR_BODY**作为属性标记, 将 IID_IStream 作为接口标识符进行传递。</span><span class="sxs-lookup"><span data-stu-id="289fc-131">Pass **PR_BODY** as the property tag and IID_IStream as the interface identifier.</span></span> <span data-ttu-id="289fc-132">有关详细信息, 请参阅[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="289fc-132">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
3. <span data-ttu-id="289fc-133">将流中的纯文本复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="289fc-133">Copy the plain text from the stream to the appropriate place in the message form.</span></span> 
    

