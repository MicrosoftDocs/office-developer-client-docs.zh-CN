---
title: PidTagRtfSyncPrefixCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncPrefixCount
api_type:
- COM
ms.assetid: c2b15ac5-9e89-4ee2-812d-102d0b2ac56e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 61683534504b7451f126591af149d11306cff1bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357860"
---
# <a name="pidtagrtfsyncprefixcount-canonical-property"></a><span data-ttu-id="178a3-103">PidTagRtfSyncPrefixCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="178a3-103">PidTagRtfSyncPrefixCount Canonical Property</span></span>

  
  
<span data-ttu-id="178a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="178a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="178a3-105">包含邮件重要字符之前出现的可忽略字符的计数。</span><span class="sxs-lookup"><span data-stu-id="178a3-105">Contains a count of the ignorable characters that appear before the significant characters of the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="178a3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="178a3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="178a3-107">PR_RTF_SYNC_PREFIX_COUNT</span><span class="sxs-lookup"><span data-stu-id="178a3-107">PR_RTF_SYNC_PREFIX_COUNT</span></span>  <br/> |
|<span data-ttu-id="178a3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="178a3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="178a3-109">0x1010</span><span class="sxs-lookup"><span data-stu-id="178a3-109">0x1010</span></span>  <br/> |
|<span data-ttu-id="178a3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="178a3-110">Data type:</span></span>  <br/> |<span data-ttu-id="178a3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="178a3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="178a3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="178a3-112">Area:</span></span>  <br/> |<span data-ttu-id="178a3-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="178a3-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="178a3-114">备注</span><span class="sxs-lookup"><span data-stu-id="178a3-114">Remarks</span></span>

<span data-ttu-id="178a3-115">前缀字符数不包括空格。</span><span class="sxs-lookup"><span data-stu-id="178a3-115">The count of prefix characters does not include white space.</span></span>
  
<span data-ttu-id="178a3-116">此属性是 RTF 格式 (RTF) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="178a3-116">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="178a3-117">RTF 辅助属性由 [RTFSync](rtfsync.md) 函数使用，不能直接由客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="178a3-117">RTF auxiliary properties are used by the [RTFSync](rtfsync.md) function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="178a3-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="178a3-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="178a3-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="178a3-119">Protocol specifications</span></span>

<span data-ttu-id="178a3-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="178a3-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="178a3-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="178a3-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="178a3-122">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="178a3-122">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="178a3-123">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="178a3-123">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="178a3-124">头文件</span><span class="sxs-lookup"><span data-stu-id="178a3-124">Header files</span></span>

<span data-ttu-id="178a3-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="178a3-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="178a3-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="178a3-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="178a3-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="178a3-127">Mapitags.h</span></span>
  
> <span data-ttu-id="178a3-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="178a3-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="178a3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="178a3-129">See also</span></span>



[<span data-ttu-id="178a3-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="178a3-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="178a3-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="178a3-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="178a3-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="178a3-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="178a3-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="178a3-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

