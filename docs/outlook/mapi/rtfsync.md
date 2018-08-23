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
ms.openlocfilehash: 706c628241e519642209a271dce62d21b16938e8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565737"
---
# <a name="rtfsync"></a><span data-ttu-id="e1ebe-103">RTFSync</span><span class="sxs-lookup"><span data-stu-id="e1ebe-103">RTFSync</span></span>

<span data-ttu-id="e1ebe-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e1ebe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e1ebe-105">确保富文本格式 (RTF) 消息文本匹配的纯文本版本。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-105">Makes sure that the Rich Text Format (RTF) message text matches the plain text version.</span></span> <span data-ttu-id="e1ebe-106">有必要阅读 RTF 版本之前和之后修改的 RTF 版本调用此函数。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-106">It is necessary to call this function before reading the RTF version and after modifying the RTF version.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e1ebe-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="e1ebe-107">Header file:</span></span>  <br/> |<span data-ttu-id="e1ebe-108">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="e1ebe-108">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="e1ebe-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e1ebe-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="e1ebe-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="e1ebe-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="e1ebe-111">调用：</span><span class="sxs-lookup"><span data-stu-id="e1ebe-111">Called by:</span></span>  <br/> |<span data-ttu-id="e1ebe-112">RTF 感知客户端应用程序和消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="e1ebe-112">RTF-aware client applications and message store providers</span></span>  <br/> |
   
```cpp
HRESULT RTFSync(
  LPMESSAGE lpMessage,
  ULONG ulFlags,
  BOOL FAR * lpfMessageUpdated
);
```

## <a name="parameters"></a><span data-ttu-id="e1ebe-113">参数</span><span class="sxs-lookup"><span data-stu-id="e1ebe-113">Parameters</span></span>

<span data-ttu-id="e1ebe-114">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="e1ebe-114">_lpMessage_</span></span>
  
> <span data-ttu-id="e1ebe-115">[in]指向要更新的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-115">[in] Pointer to the message to be updated.</span></span>
    
<span data-ttu-id="e1ebe-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e1ebe-116">_ulFlags_</span></span>
  
> <span data-ttu-id="e1ebe-117">[in]已更改的用于指示 RTF 或纯文本邮件版本标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-117">[in] Bitmask of flags used to indicate the RTF or plain text version of the message has changed.</span></span> <span data-ttu-id="e1ebe-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e1ebe-118">The following flags can be set:</span></span>
    
  - <span data-ttu-id="e1ebe-119">RTF_SYNC_BODY_CHANGED： 已更改邮件的纯文本版本。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-119">RTF_SYNC_BODY_CHANGED: The plain text version of the message has changed.</span></span>
      
  - <span data-ttu-id="e1ebe-120">RTF_SYNC_RTF_CHANGED： 邮件的 RTF 版本已更改。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-120">RTF_SYNC_RTF_CHANGED: The RTF version of the message has changed.</span></span>
    
  <span data-ttu-id="e1ebe-121">_UlFlags_参数中的所有其他位保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-121">All other bits in the  _ulFlags_ parameter are reserved for future use.</span></span> 
    
<span data-ttu-id="e1ebe-122">_lpfMessageUpdated_</span><span class="sxs-lookup"><span data-stu-id="e1ebe-122">_lpfMessageUpdated_</span></span>
  
> <span data-ttu-id="e1ebe-123">[输出]指向指示是否已更新的消息的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-123">[out] Pointer to a variable indicating whether there is an updated message.</span></span> <span data-ttu-id="e1ebe-124">如果没有，则更新的消息，则返回 FALSE 否则，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-124">TRUE if there is an updated message, FALSE otherwise.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e1ebe-125">返回值</span><span class="sxs-lookup"><span data-stu-id="e1ebe-125">Return value</span></span>

<span data-ttu-id="e1ebe-126">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1ebe-126">S_OK</span></span> 
  
> <span data-ttu-id="e1ebe-127">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-127">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e1ebe-128">注解</span><span class="sxs-lookup"><span data-stu-id="e1ebe-128">Remarks</span></span>

<span data-ttu-id="e1ebe-129">如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或为 FALSE，然后才能调用读取**RTFSync**函数的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，应已 RTF_SYNC_BODY_更改设置标志。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-129">If the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property is missing or is FALSE, before reading the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property the **RTFSync** function should be called with the RTF_SYNC_BODY_CHANGED flag set.</span></span> 
  
<span data-ttu-id="e1ebe-130">如果**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中未设置 STORE_RTF_OK 标志，应使用 RTF_SYNC_RTF_CHANGED 标志设置修改**PR_RTF_COMPRESSED**后调用此函数。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-130">If the STORE_RTF_OK flag is not set in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property, this function should be called with the RTF_SYNC_RTF_CHANGED flag set after modifying **PR_RTF_COMPRESSED**.</span></span> 
  
<span data-ttu-id="e1ebe-131">如果**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 和**PR_RTF_COMPRESSED**已更改，应设置这两个 flags 调用**RTFSync**函数。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-131">If both **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) and **PR_RTF_COMPRESSED** have been changed, the **RTFSync** function should be called with both flags set.</span></span> 
  
<span data-ttu-id="e1ebe-132">如果_lpfMessageUpdated_参数的值设置为 TRUE，则应为邮件调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-132">If the value of the  _lpfMessageUpdated_ parameter is set to TRUE, then the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method should be called for the message.</span></span> <span data-ttu-id="e1ebe-133">如果未调用**SaveChanges** ，消息中将不保存所做的修改。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-133">If **SaveChanges** is not called, the modifications will not be saved in the message.</span></span> 
  
<span data-ttu-id="e1ebe-134">消息存储提供程序可以使用**RTFSync**保持同步的**PR_BODY**和**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-134">Message store providers can use **RTFSync** to keep the **PR_BODY** and **PR_RTF_COMPRESSED** properties synchronized.</span></span> 
  
<span data-ttu-id="e1ebe-135">有关详细信息，请参阅[消息存储提供程序支持 RTF 的文本](supporting-rtf-text-for-message-store-providers.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-135">For more information, see [Supporting RTF Text for Message Store Providers](supporting-rtf-text-for-message-store-providers.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e1ebe-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1ebe-136">See also</span></span>

- [<span data-ttu-id="e1ebe-137">WrapCompressedRTFStream</span><span class="sxs-lookup"><span data-stu-id="e1ebe-137">WrapCompressedRTFStream</span></span>](wrapcompressedrtfstream.md)

