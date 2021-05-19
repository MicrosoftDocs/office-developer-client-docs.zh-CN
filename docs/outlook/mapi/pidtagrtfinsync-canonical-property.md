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
ms.openlocfilehash: ed038faf44f350b041191373cf573e7e185337c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357874"
---
# <a name="pidtagrtfinsync-canonical-property"></a><span data-ttu-id="1f98f-103">PidTagRtfInSync 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f98f-103">PidTagRtfInSync Canonical Property</span></span>

  
  
<span data-ttu-id="1f98f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f98f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f98f-105">如果 PR_RTF_COMPRESSED  ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性具有与此消息的 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性相同的文本内容，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1f98f-105">Contains TRUE if the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property has the same text content as the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property for this message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f98f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f98f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f98f-107">PR_RTF_IN_SYNC</span><span class="sxs-lookup"><span data-stu-id="1f98f-107">PR_RTF_IN_SYNC</span></span>  <br/> |
|<span data-ttu-id="1f98f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1f98f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f98f-109">0x0E1F</span><span class="sxs-lookup"><span data-stu-id="1f98f-109">0x0E1F</span></span>  <br/> |
|<span data-ttu-id="1f98f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f98f-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f98f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="1f98f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="1f98f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f98f-112">Area:</span></span>  <br/> |<span data-ttu-id="1f98f-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="1f98f-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f98f-114">备注</span><span class="sxs-lookup"><span data-stu-id="1f98f-114">Remarks</span></span>

<span data-ttu-id="1f98f-115">TRUE 值表示 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性、此消息的纯文本版本和 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性（RTF RTF (RTF) 版本）相同，PR_BODY 中的空格和 PR_RTF_COMPRESSED 中的 **格式** 除外。 </span><span class="sxs-lookup"><span data-stu-id="1f98f-115">A value of TRUE means that the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property, the plain text version of this message, and the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, the Rich Text Format (RTF) version, are identical except for white space in **PR_BODY** and formatting in **PR_RTF_COMPRESSED**.</span></span> <span data-ttu-id="1f98f-116">两个版本中的文本由同一序列中的相同字符组成。</span><span class="sxs-lookup"><span data-stu-id="1f98f-116">The text in the two versions consists of the same characters in the same sequence.</span></span>
  
<span data-ttu-id="1f98f-117">FALSE 值表示两个版本不同步文本内容，但能够由 [RTFSync](rtfsync.md) 函数进行同步。</span><span class="sxs-lookup"><span data-stu-id="1f98f-117">A value of FALSE means that the two versions are not synchronized for text content but are capable of being synchronized by the [RTFSync](rtfsync.md) function.</span></span> <span data-ttu-id="1f98f-118">一个版本已被更改，另一个版本尚未更改。</span><span class="sxs-lookup"><span data-stu-id="1f98f-118">One version has been altered and the other version has not.</span></span> 
  
<span data-ttu-id="1f98f-119">没有值意味着两个版本（如果存在或曾经存在）无法同步。</span><span class="sxs-lookup"><span data-stu-id="1f98f-119">No value means that the two versions, if both exist or ever existed, cannot be synchronized.</span></span> <span data-ttu-id="1f98f-120">一个版本已被删除或改变，因此无法再进行同步。</span><span class="sxs-lookup"><span data-stu-id="1f98f-120">One version has been deleted or altered so radically that synchronization is no longer possible.</span></span>
  
<span data-ttu-id="1f98f-121">已修改此 **PR_RTF_COMPRESSED应在此属性** 中设置 FALSE 值以强制同步。</span><span class="sxs-lookup"><span data-stu-id="1f98f-121">A client application that has modified **PR_RTF_COMPRESSED** should set a value of FALSE in this property to force synchronization.</span></span> <span data-ttu-id="1f98f-122">RTF 感知邮件存储应在 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)调用期间使用 **RTFSync** 执行同步。</span><span class="sxs-lookup"><span data-stu-id="1f98f-122">RTF-aware message stores should perform the synchronization using **RTFSync** during an [IMAPIProp::SaveChanges](imapiprop-savechanges.md) call.</span></span> <span data-ttu-id="1f98f-123">RTF 感知客户端应先检查 PR_RTF_IN_SYNC **的设置，** 然后再PR_RTF_COMPRESSED调用 **RTFSync（** 如有必要）。</span><span class="sxs-lookup"><span data-stu-id="1f98f-123">RTF-aware clients should check the setting of **PR_RTF_IN_SYNC** before reading **PR_RTF_COMPRESSED**, and call **RTFSync** first if necessary.</span></span> 
  
<span data-ttu-id="1f98f-124">如果 **PR_BODY** 对空格外的其他任何内容进行了修改，则邮件存储必须删除 **PR_RTF_IN_SYNC终止同步** 。</span><span class="sxs-lookup"><span data-stu-id="1f98f-124">If **PR_BODY** has had modifications to anything other than its white space, the message store must delete **PR_RTF_IN_SYNC** to terminate synchronization.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1f98f-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f98f-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1f98f-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="1f98f-126">Protocol specifications</span></span>

<span data-ttu-id="1f98f-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f98f-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f98f-128">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="1f98f-128">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1f98f-129">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f98f-129">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f98f-130">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="1f98f-130">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1f98f-131">头文件</span><span class="sxs-lookup"><span data-stu-id="1f98f-131">Header files</span></span>

<span data-ttu-id="1f98f-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f98f-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f98f-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f98f-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f98f-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f98f-134">Mapitags.h</span></span>
  
> <span data-ttu-id="1f98f-135">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f98f-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f98f-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f98f-136">See also</span></span>



[<span data-ttu-id="1f98f-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f98f-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f98f-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f98f-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f98f-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f98f-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f98f-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f98f-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

