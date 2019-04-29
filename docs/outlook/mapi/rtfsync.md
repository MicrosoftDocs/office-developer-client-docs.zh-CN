---
title: RTFSync
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- RTFSync
api_type:
- HeaderDef
ms.assetid: 627f95e9-39ac-4d43-8f02-687783b09785
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfdf1068caaab3894b1b489d53ccc8debe1b3a29
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436207"
---
# <a name="rtfsync"></a><span data-ttu-id="b9cca-103">RTFSync</span><span class="sxs-lookup"><span data-stu-id="b9cca-103">RTFSync</span></span>

<span data-ttu-id="b9cca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9cca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9cca-105">确保 rtf 格式 (rtf) 邮件文本与纯文本版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="b9cca-105">Makes sure that the Rich Text Format (RTF) message text matches the plain text version.</span></span> <span data-ttu-id="b9cca-106">在阅读 rtf 版本和修改 rtf 版本之后, 必须调用此函数。</span><span class="sxs-lookup"><span data-stu-id="b9cca-106">It is necessary to call this function before reading the RTF version and after modifying the RTF version.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9cca-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b9cca-107">Header file:</span></span>  <br/> |<span data-ttu-id="b9cca-108">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="b9cca-108">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b9cca-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="b9cca-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="b9cca-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="b9cca-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="b9cca-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="b9cca-111">Called by:</span></span>  <br/> |<span data-ttu-id="b9cca-112">RTF 感知客户端应用程序和邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="b9cca-112">RTF-aware client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT RTFSync(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  BOOL FAR * lpfMessageUpdated
);
```

## <a name="parameters"></a><span data-ttu-id="b9cca-113">参数</span><span class="sxs-lookup"><span data-stu-id="b9cca-113">Parameters</span></span>

<span data-ttu-id="b9cca-114">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="b9cca-114">_lpMessage_</span></span>
  
> <span data-ttu-id="b9cca-115">实时指向要更新的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="b9cca-115">[in] Pointer to the message to be updated.</span></span>
    
<span data-ttu-id="b9cca-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b9cca-116">_ulFlags_</span></span>
  
> <span data-ttu-id="b9cca-117">实时标记的位掩码, 用于指示邮件的 RTF 或纯文本版本已更改。</span><span class="sxs-lookup"><span data-stu-id="b9cca-117">[in] Bitmask of flags used to indicate the RTF or plain text version of the message has changed.</span></span> <span data-ttu-id="b9cca-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b9cca-118">The following flags can be set:</span></span>
    
  - <span data-ttu-id="b9cca-119">RTF_SYNC_BODY_CHANGED: 邮件的纯文本版本已更改。</span><span class="sxs-lookup"><span data-stu-id="b9cca-119">RTF_SYNC_BODY_CHANGED: The plain text version of the message has changed.</span></span>
      
  - <span data-ttu-id="b9cca-120">RTF_SYNC_RTF_CHANGED: 邮件的 RTF 版本已更改。</span><span class="sxs-lookup"><span data-stu-id="b9cca-120">RTF_SYNC_RTF_CHANGED: The RTF version of the message has changed.</span></span>
    
  <span data-ttu-id="b9cca-121">_ulFlags_参数中的其他所有位都将保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="b9cca-121">All other bits in the  _ulFlags_ parameter are reserved for future use.</span></span> 
    
<span data-ttu-id="b9cca-122">_lpfMessageUpdated_</span><span class="sxs-lookup"><span data-stu-id="b9cca-122">_lpfMessageUpdated_</span></span>
  
> <span data-ttu-id="b9cca-123">排除指向一个变量的指针, 该变量指示是否有更新的邮件。</span><span class="sxs-lookup"><span data-stu-id="b9cca-123">[out] Pointer to a variable indicating whether there is an updated message.</span></span> <span data-ttu-id="b9cca-124">如果有更新的邮件, 则为 TRUE, 否则为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b9cca-124">TRUE if there is an updated message, FALSE otherwise.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b9cca-125">返回值</span><span class="sxs-lookup"><span data-stu-id="b9cca-125">Return value</span></span>

<span data-ttu-id="b9cca-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9cca-126">S_OK</span></span> 
  
> <span data-ttu-id="b9cca-127">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="b9cca-127">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b9cca-128">说明</span><span class="sxs-lookup"><span data-stu-id="b9cca-128">Remarks</span></span>

<span data-ttu-id="b9cca-129">如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或为 FALSE, 则在读取**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性之前, 应使用 RTFSync 调用**RTF_SYNC_BODY_** 函数已更改的标志集。</span><span class="sxs-lookup"><span data-stu-id="b9cca-129">If the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property is missing or is FALSE, before reading the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property the **RTFSync** function should be called with the RTF_SYNC_BODY_CHANGED flag set.</span></span> 
  
<span data-ttu-id="b9cca-130">如果**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中未设置 STORE_RTF_OK 标志, 则应在修改**PR_RTF_COMPRESSED**后设置 RTF_SYNC_RTF_CHANGED 标志来调用此函数。</span><span class="sxs-lookup"><span data-stu-id="b9cca-130">If the STORE_RTF_OK flag is not set in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property, this function should be called with the RTF_SYNC_RTF_CHANGED flag set after modifying **PR_RTF_COMPRESSED**.</span></span> 
  
<span data-ttu-id="b9cca-131">如果同时更改了**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED** , 则应使用这两个标志集调用**RTFSync**函数。</span><span class="sxs-lookup"><span data-stu-id="b9cca-131">If both **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) and **PR_RTF_COMPRESSED** have been changed, the **RTFSync** function should be called with both flags set.</span></span> 
  
<span data-ttu-id="b9cca-132">如果将_lpfMessageUpdated_参数的值设置为 TRUE, 则应为邮件调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b9cca-132">If the value of the  _lpfMessageUpdated_ parameter is set to TRUE, then the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method should be called for the message.</span></span> <span data-ttu-id="b9cca-133">如果未调用**SaveChanges** , 修改将不会保存在邮件中。</span><span class="sxs-lookup"><span data-stu-id="b9cca-133">If **SaveChanges** is not called, the modifications will not be saved in the message.</span></span> 
  
<span data-ttu-id="b9cca-134">邮件存储提供程序可以使用**RTFSync**保持**PR_BODY**和**PR_RTF_COMPRESSED**属性同步。</span><span class="sxs-lookup"><span data-stu-id="b9cca-134">Message store providers can use **RTFSync** to keep the **PR_BODY** and **PR_RTF_COMPRESSED** properties synchronized.</span></span> 
  
<span data-ttu-id="b9cca-135">有关详细信息, 请参阅[支持邮件存储提供程序的 RTF 文本](supporting-rtf-text-for-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b9cca-135">For more information, see [Supporting RTF Text for Message Store Providers](supporting-rtf-text-for-message-store-providers.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9cca-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9cca-136">See also</span></span>

- [<span data-ttu-id="b9cca-137">WrapCompressedRTFStream</span><span class="sxs-lookup"><span data-stu-id="b9cca-137">WrapCompressedRTFStream</span></span>](wrapcompressedrtfstream.md)

