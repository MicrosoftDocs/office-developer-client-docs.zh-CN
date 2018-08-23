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
ms.openlocfilehash: 32344d81d929b0f78a5f883cd9860d838ba25bb8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568439"
---
# <a name="pidtagrtfsyncprefixcount-canonical-property"></a><span data-ttu-id="80fa5-103">PidTagRtfSyncPrefixCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="80fa5-103">PidTagRtfSyncPrefixCount Canonical Property</span></span>

  
  
<span data-ttu-id="80fa5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80fa5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80fa5-105">包含可忽略出现在邮件的重要字符之前的字符数。</span><span class="sxs-lookup"><span data-stu-id="80fa5-105">Contains a count of the ignorable characters that appear before the significant characters of the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="80fa5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="80fa5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="80fa5-107">PR_RTF_SYNC_PREFIX_COUNT</span><span class="sxs-lookup"><span data-stu-id="80fa5-107">PR_RTF_SYNC_PREFIX_COUNT</span></span>  <br/> |
|<span data-ttu-id="80fa5-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="80fa5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="80fa5-109">0x1010</span><span class="sxs-lookup"><span data-stu-id="80fa5-109">0x1010</span></span>  <br/> |
|<span data-ttu-id="80fa5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="80fa5-110">Data type:</span></span>  <br/> |<span data-ttu-id="80fa5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="80fa5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="80fa5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="80fa5-112">Area:</span></span>  <br/> |<span data-ttu-id="80fa5-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="80fa5-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="80fa5-114">注解</span><span class="sxs-lookup"><span data-stu-id="80fa5-114">Remarks</span></span>

<span data-ttu-id="80fa5-115">前缀字符数不包括空格。</span><span class="sxs-lookup"><span data-stu-id="80fa5-115">The count of prefix characters does not include white space.</span></span>
  
<span data-ttu-id="80fa5-116">此属性是一个富文本格式 (RTF) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="80fa5-116">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="80fa5-117">RTF 辅助属性使用[RTFSync](rtfsync.md)函数和不能直接使用客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="80fa5-117">RTF auxiliary properties are used by the [RTFSync](rtfsync.md) function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="80fa5-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="80fa5-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="80fa5-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="80fa5-119">Protocol specifications</span></span>

<span data-ttu-id="80fa5-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="80fa5-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="80fa5-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="80fa5-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="80fa5-122">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="80fa5-122">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="80fa5-123">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="80fa5-123">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="80fa5-124">头文件</span><span class="sxs-lookup"><span data-stu-id="80fa5-124">Header files</span></span>

<span data-ttu-id="80fa5-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="80fa5-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="80fa5-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="80fa5-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="80fa5-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="80fa5-127">Mapitags.h</span></span>
  
> <span data-ttu-id="80fa5-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="80fa5-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="80fa5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80fa5-129">See also</span></span>



[<span data-ttu-id="80fa5-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="80fa5-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="80fa5-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="80fa5-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="80fa5-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="80fa5-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="80fa5-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="80fa5-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

