---
title: PidTagRtfInSync 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfInSync
api_type:
- COM
ms.assetid: 443cc68e-7898-4285-a606-f916fcd18554
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b182d2b568a3c7cf874dfe2fcf7a7503aa44193f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574487"
---
# <a name="pidtagrtfinsync-canonical-property"></a><span data-ttu-id="9dbf7-103">PidTagRtfInSync 规范属性</span><span class="sxs-lookup"><span data-stu-id="9dbf7-103">PidTagRtfInSync Canonical Property</span></span>

  
  
<span data-ttu-id="9dbf7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9dbf7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9dbf7-105">如果**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性具有相同的文本内容此消息的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-105">Contains TRUE if the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property has the same text content as the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9dbf7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9dbf7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9dbf7-107">PR_RTF_IN_SYNC</span><span class="sxs-lookup"><span data-stu-id="9dbf7-107">PR_RTF_IN_SYNC</span></span>  <br/> |
|<span data-ttu-id="9dbf7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9dbf7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9dbf7-109">0x0E1F</span><span class="sxs-lookup"><span data-stu-id="9dbf7-109">0x0E1F</span></span>  <br/> |
|<span data-ttu-id="9dbf7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9dbf7-110">Data type:</span></span>  <br/> |<span data-ttu-id="9dbf7-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="9dbf7-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="9dbf7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9dbf7-112">Area:</span></span>  <br/> |<span data-ttu-id="9dbf7-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="9dbf7-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9dbf7-114">注解</span><span class="sxs-lookup"><span data-stu-id="9dbf7-114">Remarks</span></span>

<span data-ttu-id="9dbf7-115">值为 TRUE 表示**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，此消息的纯文本版本和**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，富文本格式 (RTF) 版本中，完全相同的除外**PR_BODY**和中**PR_RTF_COMPRESSED**格式中的空格。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-115">A value of TRUE means that the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, the plain text version of this message, and the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, the Rich Text Format (RTF) version, are identical except for white space in **PR_BODY** and formatting in **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="9dbf7-116">两个版本中的文本包含的顺序相同的字符。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-116">The text in the two versions consists of the same characters in the same sequence.</span></span>
  
<span data-ttu-id="9dbf7-117">值为 FALSE 表示的两个版本不同步的文本内容，但能够在同步[RTFSync](rtfsync.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-117">A value of FALSE means that the two versions are not synchronized for text content but are capable of being synchronized by the [RTFSync](rtfsync.md) function.</span></span> <span data-ttu-id="9dbf7-118">已更改一个版本和其他版本却没有。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-118">One version has been altered and the other version has not.</span></span> 
  
<span data-ttu-id="9dbf7-119">没有值表示的两个版本中，如果同时存在或以往任何时候都存在，无法同步。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-119">No value means that the two versions, if both exist or ever existed, cannot be synchronized.</span></span> <span data-ttu-id="9dbf7-120">已删除或修改大大同步不再可能一个版本。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-120">One version has been deleted or altered so radically that synchronization is no longer possible.</span></span>
  
<span data-ttu-id="9dbf7-121">已修改**PR_RTF_COMPRESSED**客户端应用程序应设置的值为 FALSE 以强制执行同步此属性中。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-121">A client application that has modified **PR_RTF_COMPRESSED** should set a value of FALSE in this property to force synchronization.</span></span> <span data-ttu-id="9dbf7-122">RTF 感知消息存储应执行[IMAPIProp::SaveChanges](imapiprop-savechanges.md)呼叫期间使用**RTFSync**同步。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-122">RTF-aware message stores should perform the synchronization using **RTFSync** during an [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call.</span></span> <span data-ttu-id="9dbf7-123">RTF 感知客户端应检查**PR_RTF_IN_SYNC**阅读**PR_RTF_COMPRESSED**之前, 的设置，并首先呼叫**RTFSync** ，如有必要。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-123">RTF-aware clients should check the setting of **PR_RTF_IN_SYNC** before reading **PR_RTF_COMPRESSED**, and call **RTFSync** first if necessary.</span></span> 
  
<span data-ttu-id="9dbf7-124">如果**PR_BODY**已为其空格以外的任何修改，消息存储库必须删除**PR_RTF_IN_SYNC**终止同步。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-124">If **PR_BODY** has had modifications to anything other than its white space, the message store must delete **PR_RTF_IN_SYNC** to terminate synchronization.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9dbf7-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="9dbf7-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9dbf7-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="9dbf7-126">Protocol specifications</span></span>

<span data-ttu-id="9dbf7-127">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9dbf7-127">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9dbf7-128">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9dbf7-129">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9dbf7-129">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9dbf7-130">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-130">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9dbf7-131">头文件</span><span class="sxs-lookup"><span data-stu-id="9dbf7-131">Header files</span></span>

<span data-ttu-id="9dbf7-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9dbf7-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="9dbf7-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="9dbf7-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9dbf7-134">Mapitags.h</span></span>
  
> <span data-ttu-id="9dbf7-135">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9dbf7-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9dbf7-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbf7-136">See also</span></span>



[<span data-ttu-id="9dbf7-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9dbf7-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9dbf7-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9dbf7-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9dbf7-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9dbf7-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9dbf7-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9dbf7-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

