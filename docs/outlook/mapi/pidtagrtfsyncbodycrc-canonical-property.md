---
title: PidTagRtfSyncBodyCrc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncBodyCrc
api_type:
- COM
ms.assetid: 95db4837-400f-476f-b313-60e8baa1c6d1
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: aa144ca93e8fad9b9b5a5da1ee457e5cc3bbd841
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778267"
---
# <a name="pidtagrtfsyncbodycrc-canonical-property"></a><span data-ttu-id="7551c-103">PidTagRtfSyncBodyCrc 规范属性</span><span class="sxs-lookup"><span data-stu-id="7551c-103">PidTagRtfSyncBodyCrc Canonical Property</span></span>

  
  
<span data-ttu-id="7551c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7551c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7551c-105">包含的邮件文本计算循环冗余检查 (CRC)。</span><span class="sxs-lookup"><span data-stu-id="7551c-105">Contains the cyclical redundancy check (CRC) computed for the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7551c-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="7551c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7551c-107">PR_RTF_SYNC_BODY_CRC</span><span class="sxs-lookup"><span data-stu-id="7551c-107">PR_RTF_SYNC_BODY_CRC</span></span>  <br/> |
|<span data-ttu-id="7551c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7551c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7551c-109">0x1006</span><span class="sxs-lookup"><span data-stu-id="7551c-109">0x1006</span></span>  <br/> |
|<span data-ttu-id="7551c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7551c-110">Data type:</span></span>  <br/> |<span data-ttu-id="7551c-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7551c-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7551c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7551c-112">Area:</span></span>  <br/> |<span data-ttu-id="7551c-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="7551c-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7551c-114">备注</span><span class="sxs-lookup"><span data-stu-id="7551c-114">Remarks</span></span>

<span data-ttu-id="7551c-115">[RTFSync](rtfsync.md)函数计算 CRC 使用其认为是重要邮件的字符。</span><span class="sxs-lookup"><span data-stu-id="7551c-115">The [RTFSync](rtfsync.md) function computes the CRC by using only the characters that it considers to be significant to the message.</span></span> <span data-ttu-id="7551c-116">例如，从 CRC 忽略一些空格和其他可忽略字符。</span><span class="sxs-lookup"><span data-stu-id="7551c-116">For example, some white space and other ignorable characters are omitted from the CRC.</span></span> 
  
<span data-ttu-id="7551c-117">此属性是一个富文本格式 (RTF) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="7551c-117">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="7551c-118">这些属性使用**RTFSync**函数，不能直接通过客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="7551c-118">These properties are used by the **RTFSync** function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7551c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="7551c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7551c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="7551c-120">Protocol specifications</span></span>

<span data-ttu-id="7551c-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7551c-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7551c-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="7551c-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7551c-123">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7551c-123">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7551c-124">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="7551c-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7551c-125">头文件</span><span class="sxs-lookup"><span data-stu-id="7551c-125">Header files</span></span>

<span data-ttu-id="7551c-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7551c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="7551c-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7551c-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="7551c-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7551c-128">Mapitags.h</span></span>
  
> <span data-ttu-id="7551c-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7551c-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7551c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7551c-130">See also</span></span>



[<span data-ttu-id="7551c-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7551c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7551c-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7551c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7551c-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7551c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7551c-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7551c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
