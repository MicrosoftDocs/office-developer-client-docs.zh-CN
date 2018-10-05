---
title: PidTagRtfSyncBodyTag 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyTag
api_type:
- COM
ms.assetid: 2dab5018-4214-4162-93bc-e5565f3ac24c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24ef1d4e3e936426aea8216119e8ada9f6122e95
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387508"
---
# <a name="pidtagrtfsyncbodytag-canonical-property"></a><span data-ttu-id="e2899-103">PidTagRtfSyncBodyTag 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2899-103">PidTagRtfSyncBodyTag Canonical Property</span></span>

  
  
<span data-ttu-id="e2899-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2899-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2899-105">包含出现在消息文本的开头的有效字符。</span><span class="sxs-lookup"><span data-stu-id="e2899-105">Contains significant characters that appear at the beginning of the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e2899-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e2899-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e2899-107">PR_RTF_SYNC_BODY_TAG，PR_RTF_SYNC_BODY_TAG_A，PR_RTF_SYNC_BODY_TAG_W</span><span class="sxs-lookup"><span data-stu-id="e2899-107">PR_RTF_SYNC_BODY_TAG, PR_RTF_SYNC_BODY_TAG_A, PR_RTF_SYNC_BODY_TAG_W</span></span>  <br/> |
|<span data-ttu-id="e2899-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e2899-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e2899-109">0x1008</span><span class="sxs-lookup"><span data-stu-id="e2899-109">0x1008</span></span>  <br/> |
|<span data-ttu-id="e2899-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e2899-110">Data type:</span></span>  <br/> |<span data-ttu-id="e2899-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e2899-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e2899-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e2899-112">Area:</span></span>  <br/> |<span data-ttu-id="e2899-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="e2899-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e2899-114">说明</span><span class="sxs-lookup"><span data-stu-id="e2899-114">Remarks</span></span>

<span data-ttu-id="e2899-115">[RTFSync](rtfsync.md)函数使用的文本标记指示消息文本的开头。</span><span class="sxs-lookup"><span data-stu-id="e2899-115">The [RTFSync](rtfsync.md) function uses the text tag to indicate the beginning of the message text.</span></span> <span data-ttu-id="e2899-116">修改文本时，标记用于查找以前的文本的开头。</span><span class="sxs-lookup"><span data-stu-id="e2899-116">When the text is modified, the tag is used to find the beginning of the previous text.</span></span> 
  
<span data-ttu-id="e2899-117">这些属性是富文本格式辅助属性。</span><span class="sxs-lookup"><span data-stu-id="e2899-117">These properties are Rich Text Format auxiliary properties.</span></span> <span data-ttu-id="e2899-118">他们使用**RTFSync**函数并不能直接使用客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2899-118">They are used by the **RTFSync** function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e2899-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e2899-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e2899-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="e2899-120">Protocol specifications</span></span>

<span data-ttu-id="e2899-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2899-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2899-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e2899-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e2899-123">[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2899-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e2899-124">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="e2899-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e2899-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e2899-125">Header files</span></span>

<span data-ttu-id="e2899-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e2899-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e2899-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e2899-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="e2899-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e2899-128">Mapitags.h</span></span>
  
> <span data-ttu-id="e2899-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e2899-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2899-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2899-130">See also</span></span>



[<span data-ttu-id="e2899-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e2899-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e2899-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e2899-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e2899-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e2899-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e2899-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e2899-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

