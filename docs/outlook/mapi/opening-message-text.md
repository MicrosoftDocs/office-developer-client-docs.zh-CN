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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407534"
---
# <a name="opening-message-text"></a><span data-ttu-id="8197b-103">打开邮件文本</span><span class="sxs-lookup"><span data-stu-id="8197b-103">Opening message text</span></span>

<span data-ttu-id="8197b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8197b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8197b-105">邮件的文本存储在其 **PR \_ BODY** 属性或 **PR \_ RTF \_ COMPRESSED 属性** 中。</span><span class="sxs-lookup"><span data-stu-id="8197b-105">The text of a message is stored either in its **PR\_BODY** property or **PR\_RTF\_COMPRESSED** property.</span></span> <span data-ttu-id="8197b-106">有关详细信息，请参阅 **PR \_ BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 、PR **\_ HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)) 和 **PR \_ RTF \_ COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="8197b-106">For more information, see **PR\_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), **PR\_HTML** ([PidTagHtml](pidtaghtml-canonical-property.md)), and **PR\_RTF\_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> 

<span data-ttu-id="8197b-107">如果支持 RTF 格式格式 (RTF) ，请打开 **PR \_ RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="8197b-107">If you support the Rich Text Format (RTF), open **PR\_RTF_COMPRESSED**.</span></span> <span data-ttu-id="8197b-108">如果不支持 RTF，请打开 **PR \_ BODY**。</span><span class="sxs-lookup"><span data-stu-id="8197b-108">If you do not support RTF, open **PR\_BODY**.</span></span> <span data-ttu-id="8197b-109">由于无论邮件是否设置格式，邮件文本都可以很大，因此使用 **IMAPIProp：：OpenProperty** 打开这些属性。</span><span class="sxs-lookup"><span data-stu-id="8197b-109">Because the text of a message can be large regardless of whether or not it is formatted, use **IMAPIProp::OpenProperty** to open these properties.</span></span> <span data-ttu-id="8197b-110">有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-110">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
  
### <a name="to-display-formatted-message-text"></a><span data-ttu-id="8197b-111">显示带格式的邮件文本</span><span class="sxs-lookup"><span data-stu-id="8197b-111">To display formatted message text</span></span>
  
1. <span data-ttu-id="8197b-112">如果您使用的是非 RTF 感知邮件存储，如存储的 STORE_RTF_OK PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 指示： </span><span class="sxs-lookup"><span data-stu-id="8197b-112">If you are using a non-RTF aware message store, as indicated by the absence of the STORE_RTF_OK flag in the store's **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
    
    1. <span data-ttu-id="8197b-113">调用邮件的 **IMAPIProp：：GetProps** 方法来检索 PR_RTF_IN_SYNC **属性。**</span><span class="sxs-lookup"><span data-stu-id="8197b-113">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_RTF_IN_SYNC** property.</span></span> <span data-ttu-id="8197b-114">有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="8197b-114">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md) and **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)).</span></span>
        
    2. <span data-ttu-id="8197b-115">调用 RTFSync 以将邮件的 PR_BODY 属性与 **PR_RTF_COMPRESSED** 属性同步。</span><span class="sxs-lookup"><span data-stu-id="8197b-115">Call RTFSync to synchronize the message's PR_BODY property with the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="8197b-116">有关详细信息，请参阅 [RTFSync、PR_BODY](rtfsync.md)和 **PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="8197b-116">For more information, see [RTFSync](rtfsync.md), **PR_BODY**, and **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="8197b-117">如果RTF_SYNC_BODY_CHANGED检索的调用由于属性不存在或 **设置为** FALSE 而PR_RTF_IN_SYNC，请传递该标记。</span><span class="sxs-lookup"><span data-stu-id="8197b-117">Pass the RTF_SYNC_BODY_CHANGED flag if the call to retrieve **PR_RTF_IN_SYNC** failed because the property does not exist or it is set to FALSE.</span></span> 
        
    3. <span data-ttu-id="8197b-118">如果 **RTFSync** 返回 TRUE（指示进行了更改），请调用消息的 **IMAPIProp：：SaveChanges** 方法来永久存储它们。</span><span class="sxs-lookup"><span data-stu-id="8197b-118">If **RTFSync** returned TRUE — indicating that changes were made — call the message's **IMAPIProp::SaveChanges** method to permanently store them.</span></span> <span data-ttu-id="8197b-119">有关详细信息，请参阅 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-119">For more information, see [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
2. <span data-ttu-id="8197b-120">无论你是否使用 RTF 感知邮件存储：</span><span class="sxs-lookup"><span data-stu-id="8197b-120">Regardless of whether or not you are using an RTF-aware message store:</span></span>
    
    1. <span data-ttu-id="8197b-121">调用 **IMAPIProp：：OpenProperty** 以打开 **PR_RTF_COMPRESSED** 属性。</span><span class="sxs-lookup"><span data-stu-id="8197b-121">Call **IMAPIProp::OpenProperty** to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="8197b-122">有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**。</span><span class="sxs-lookup"><span data-stu-id="8197b-122">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md) and **PR_RTF_COMPRESSED**.</span></span>
        
    2. <span data-ttu-id="8197b-123">如果 **PR_RTF_COMPRESSED** 不可用，请调用 **OpenProperty** 以打开 **PR_BODY** 属性。</span><span class="sxs-lookup"><span data-stu-id="8197b-123">If **PR_RTF_COMPRESSED** is not available, call **OpenProperty** to open the **PR_BODY** property.</span></span> 
        
    3. <span data-ttu-id="8197b-124">调用 **WrapCompressedRTFStream** 函数以创建压缩 RTF 数据的未压缩版本（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="8197b-124">Call the **WrapCompressedRTFStream** function to create an uncompressed version of the compressed RTF data, if available.</span></span> <span data-ttu-id="8197b-125">有关详细信息，请参阅 [WrapCompressedRTFStream](wrapcompressedrtfstream.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-125">For more information, see [WrapCompressedRTFStream](wrapcompressedrtfstream.md).</span></span>
        
    4. <span data-ttu-id="8197b-126">将格式化的文本从流复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="8197b-126">Copy the formatted text from the stream to the appropriate place in the message form.</span></span> 
    
### <a name="to-display-plain-message-text"></a><span data-ttu-id="8197b-127">显示纯消息文本</span><span class="sxs-lookup"><span data-stu-id="8197b-127">To display plain message text</span></span>
  
1. <span data-ttu-id="8197b-128">调用邮件的 **IMAPIProp：：GetProps** 方法来检索 PR_BODY **属性。**</span><span class="sxs-lookup"><span data-stu-id="8197b-128">Call the message's **IMAPIProp::GetProps** method to retrieve the **PR_BODY** property.</span></span> <span data-ttu-id="8197b-129">有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-129">For more information, see [IMAPIProp::GetProps](imapiprop-getprops.md).</span></span>
    
2. <span data-ttu-id="8197b-130">如果 **GetProps** 返回PT_ERROR值结构中属性类型的值或MAPI_E_NOT_ENOUGH_MEMORY，请调用消息的 **IMAPIProp：：OpenProperty** 方法。</span><span class="sxs-lookup"><span data-stu-id="8197b-130">If **GetProps** returns either PT_ERROR for the property type in the property value structure or MAPI_E_NOT_ENOUGH_MEMORY, call the message's **IMAPIProp::OpenProperty** method.</span></span> <span data-ttu-id="8197b-131">将 **PR_BODY** 作为属性标记传递，IID_IStream作为接口标识符传递。</span><span class="sxs-lookup"><span data-stu-id="8197b-131">Pass **PR_BODY** as the property tag and IID_IStream as the interface identifier.</span></span> <span data-ttu-id="8197b-132">有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="8197b-132">For more information, see [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span>
    
3. <span data-ttu-id="8197b-133">将纯文本从流复制到邮件窗体中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="8197b-133">Copy the plain text from the stream to the appropriate place in the message form.</span></span> 
    

