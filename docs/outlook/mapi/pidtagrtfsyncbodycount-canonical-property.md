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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398799"
---
# <a name="pidtagrtfsyncbodycount-canonical-property"></a><span data-ttu-id="1ee92-103">PidTagRtfSyncBodyCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ee92-103">PidTagRtfSyncBodyCount Canonical Property</span></span>

  
  
<span data-ttu-id="1ee92-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1ee92-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1ee92-105">包含消息文本的有效字符的计数。</span><span class="sxs-lookup"><span data-stu-id="1ee92-105">Contains a count of the significant characters of the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1ee92-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1ee92-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1ee92-107">PR_RTF_SYNC_BODY_COUNT</span><span class="sxs-lookup"><span data-stu-id="1ee92-107">PR_RTF_SYNC_BODY_COUNT</span></span>  <br/> |
|<span data-ttu-id="1ee92-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1ee92-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1ee92-109">0x1007</span><span class="sxs-lookup"><span data-stu-id="1ee92-109">0x1007</span></span>  <br/> |
|<span data-ttu-id="1ee92-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1ee92-110">Data type:</span></span>  <br/> |<span data-ttu-id="1ee92-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="1ee92-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="1ee92-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1ee92-112">Area:</span></span>  <br/> |<span data-ttu-id="1ee92-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="1ee92-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1ee92-114">说明</span><span class="sxs-lookup"><span data-stu-id="1ee92-114">Remarks</span></span>

<span data-ttu-id="1ee92-115">[RTFSync](rtfsync.md)函数计算中使用仅那些其认为是重要邮件的文本的字符数。</span><span class="sxs-lookup"><span data-stu-id="1ee92-115">The [RTFSync](rtfsync.md) function computes the count of characters in the text using only those that it considers to be significant to the message.</span></span> <span data-ttu-id="1ee92-116">例如，从计数忽略一些空格和其他可忽略字符。</span><span class="sxs-lookup"><span data-stu-id="1ee92-116">For example, some white space and other ignorable characters are omitted from the count.</span></span> 
  
<span data-ttu-id="1ee92-117">此属性是一个富文本格式 (RTF) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="1ee92-117">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="1ee92-118">这些属性使用**RTFSync**函数，不能直接通过客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="1ee92-118">These properties are used by the **RTFSync** function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1ee92-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="1ee92-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1ee92-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="1ee92-120">Protocol specifications</span></span>

<span data-ttu-id="1ee92-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ee92-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ee92-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1ee92-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1ee92-123">[[MS OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1ee92-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1ee92-124">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="1ee92-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1ee92-125">头文件</span><span class="sxs-lookup"><span data-stu-id="1ee92-125">Header files</span></span>

<span data-ttu-id="1ee92-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1ee92-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="1ee92-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1ee92-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="1ee92-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1ee92-128">Mapitags.h</span></span>
  
> <span data-ttu-id="1ee92-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1ee92-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1ee92-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee92-130">See also</span></span>



[<span data-ttu-id="1ee92-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1ee92-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1ee92-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1ee92-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1ee92-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1ee92-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1ee92-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1ee92-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

