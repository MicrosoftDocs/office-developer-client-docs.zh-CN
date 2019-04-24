---
title: PidTagRtfSyncBodyCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyCount
api_type:
- COM
ms.assetid: b7267be4-8d5c-4dc7-86b2-651e03e84f9b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f6e687412dfce1e5fcee6b4a4d64f3e5106455f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331253"
---
# <a name="pidtagrtfsyncbodycount-canonical-property"></a><span data-ttu-id="0cc0c-103">PidTagRtfSyncBodyCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="0cc0c-103">PidTagRtfSyncBodyCount Canonical Property</span></span>

  
  
<span data-ttu-id="0cc0c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0cc0c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0cc0c-105">包含邮件文本的重要字符的计数。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-105">Contains a count of the significant characters of the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0cc0c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0cc0c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0cc0c-107">PR_RTF_SYNC_BODY_COUNT</span><span class="sxs-lookup"><span data-stu-id="0cc0c-107">PR_RTF_SYNC_BODY_COUNT</span></span>  <br/> |
|<span data-ttu-id="0cc0c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0cc0c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0cc0c-109">0x1007</span><span class="sxs-lookup"><span data-stu-id="0cc0c-109">0x1007</span></span>  <br/> |
|<span data-ttu-id="0cc0c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0cc0c-110">Data type:</span></span>  <br/> |<span data-ttu-id="0cc0c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0cc0c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0cc0c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0cc0c-112">Area:</span></span>  <br/> |<span data-ttu-id="0cc0c-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="0cc0c-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0cc0c-114">注解</span><span class="sxs-lookup"><span data-stu-id="0cc0c-114">Remarks</span></span>

<span data-ttu-id="0cc0c-115">[RTFSync](rtfsync.md)函数计算文本中的字符数, 仅使用它认为对邮件有意义的字符。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-115">The [RTFSync](rtfsync.md) function computes the count of characters in the text using only those that it considers to be significant to the message.</span></span> <span data-ttu-id="0cc0c-116">例如, 某些空格和其他可忽略字符将从 count 中省略。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-116">For example, some white space and other ignorable characters are omitted from the count.</span></span> 
  
<span data-ttu-id="0cc0c-117">此属性是 rtf 格式 (rtf) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-117">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="0cc0c-118">这些属性由**RTFSync**函数使用, 不应由客户端应用程序直接使用。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-118">These properties are used by the **RTFSync** function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0cc0c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="0cc0c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0cc0c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="0cc0c-120">Protocol specifications</span></span>

<span data-ttu-id="0cc0c-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0cc0c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0cc0c-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0cc0c-123">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0cc0c-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0cc0c-124">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0cc0c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="0cc0c-125">Header files</span></span>

<span data-ttu-id="0cc0c-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0cc0c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="0cc0c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="0cc0c-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0cc0c-128">Mapitags.h</span></span>
  
> <span data-ttu-id="0cc0c-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0cc0c-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0cc0c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cc0c-130">See also</span></span>



[<span data-ttu-id="0cc0c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0cc0c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0cc0c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0cc0c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0cc0c-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0cc0c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0cc0c-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0cc0c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

