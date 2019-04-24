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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85ac61d968243283e5ad9283730941adcd87cd5e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357867"
---
# <a name="pidtagrtfsyncbodycrc-canonical-property"></a><span data-ttu-id="6beb5-103">PidTagRtfSyncBodyCrc 规范属性</span><span class="sxs-lookup"><span data-stu-id="6beb5-103">PidTagRtfSyncBodyCrc Canonical Property</span></span>

  
  
<span data-ttu-id="6beb5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6beb5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6beb5-105">包含为邮件文本计算的循环冗余校验 (CRC)。</span><span class="sxs-lookup"><span data-stu-id="6beb5-105">Contains the cyclical redundancy check (CRC) computed for the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6beb5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6beb5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6beb5-107">PR_RTF_SYNC_BODY_CRC</span><span class="sxs-lookup"><span data-stu-id="6beb5-107">PR_RTF_SYNC_BODY_CRC</span></span>  <br/> |
|<span data-ttu-id="6beb5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6beb5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6beb5-109">0x1006</span><span class="sxs-lookup"><span data-stu-id="6beb5-109">0x1006</span></span>  <br/> |
|<span data-ttu-id="6beb5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6beb5-110">Data type:</span></span>  <br/> |<span data-ttu-id="6beb5-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6beb5-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6beb5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6beb5-112">Area:</span></span>  <br/> |<span data-ttu-id="6beb5-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="6beb5-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6beb5-114">注解</span><span class="sxs-lookup"><span data-stu-id="6beb5-114">Remarks</span></span>

<span data-ttu-id="6beb5-115">[RTFSync](rtfsync.md)函数通过仅使用它认为对邮件有意义的字符来计算 CRC。</span><span class="sxs-lookup"><span data-stu-id="6beb5-115">The [RTFSync](rtfsync.md) function computes the CRC by using only the characters that it considers to be significant to the message.</span></span> <span data-ttu-id="6beb5-116">例如, 某些空格和其他可忽略的字符将从 CRC 中省略。</span><span class="sxs-lookup"><span data-stu-id="6beb5-116">For example, some white space and other ignorable characters are omitted from the CRC.</span></span> 
  
<span data-ttu-id="6beb5-117">此属性是 rtf 格式 (rtf) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="6beb5-117">This property is a Rich Text Format (RTF) auxiliary property.</span></span> <span data-ttu-id="6beb5-118">这些属性由**RTFSync**函数使用, 不应由客户端应用程序直接使用。</span><span class="sxs-lookup"><span data-stu-id="6beb5-118">These properties are used by the **RTFSync** function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6beb5-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="6beb5-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6beb5-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="6beb5-120">Protocol specifications</span></span>

<span data-ttu-id="6beb5-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6beb5-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6beb5-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6beb5-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6beb5-123">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6beb5-123">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6beb5-124">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="6beb5-124">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6beb5-125">头文件</span><span class="sxs-lookup"><span data-stu-id="6beb5-125">Header files</span></span>

<span data-ttu-id="6beb5-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6beb5-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="6beb5-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6beb5-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="6beb5-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="6beb5-128">Mapitags.h</span></span>
  
> <span data-ttu-id="6beb5-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6beb5-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6beb5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6beb5-130">See also</span></span>



[<span data-ttu-id="6beb5-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6beb5-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6beb5-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6beb5-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6beb5-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6beb5-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6beb5-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6beb5-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

