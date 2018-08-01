---
title: PidTagRtfSyncTrailingCount 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfSyncTrailingCount
api_type:
- COM
ms.assetid: 3f0e5b24-767e-46f5-bb3d-e9cb82cb935b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3174ebbcf70104c82305e2a20df1e183d30265d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778258"
---
# <a name="pidtagrtfsynctrailingcount-canonical-property"></a><span data-ttu-id="90533-103">PidTagRtfSyncTrailingCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="90533-103">PidTagRtfSyncTrailingCount Canonical Property</span></span>

  
  
<span data-ttu-id="90533-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="90533-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="90533-105">包含可忽略重要个字符的消息后显示的字符数。</span><span class="sxs-lookup"><span data-stu-id="90533-105">Contains a count of the ignorable characters that appear after the significant characters of the message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="90533-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="90533-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="90533-107">PR_RTF_SYNC_TRAILING_COUNT</span><span class="sxs-lookup"><span data-stu-id="90533-107">PR_RTF_SYNC_TRAILING_COUNT</span></span>  <br/> |
|<span data-ttu-id="90533-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="90533-108">Identifier:</span></span>  <br/> |<span data-ttu-id="90533-109">0x1011</span><span class="sxs-lookup"><span data-stu-id="90533-109">0x1011</span></span>  <br/> |
|<span data-ttu-id="90533-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="90533-110">Data type:</span></span>  <br/> |<span data-ttu-id="90533-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="90533-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="90533-112">区域：</span><span class="sxs-lookup"><span data-stu-id="90533-112">Area:</span></span>  <br/> |<span data-ttu-id="90533-113">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="90533-113">MAPI message</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90533-114">说明</span><span class="sxs-lookup"><span data-stu-id="90533-114">Remarks</span></span>

<span data-ttu-id="90533-115">此属性是一个富文本格式 (RFT) 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="90533-115">This property is a Rich Text Format (RFT) auxiliary property.</span></span> <span data-ttu-id="90533-116">这些属性使用[RTFSync](rtfsync.md)函数，不能直接通过客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="90533-116">These properties are used by the [RTFSync](rtfsync.md) function and are not intended to be used directly by client applications.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="90533-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="90533-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="90533-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="90533-118">Protocol specifications</span></span>

<span data-ttu-id="90533-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90533-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90533-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="90533-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="90533-121">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90533-121">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90533-122">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="90533-122">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="90533-123">头文件</span><span class="sxs-lookup"><span data-stu-id="90533-123">Header files</span></span>

<span data-ttu-id="90533-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="90533-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="90533-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="90533-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="90533-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="90533-126">Mapitags.h</span></span>
  
> <span data-ttu-id="90533-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="90533-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="90533-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90533-128">See also</span></span>



[<span data-ttu-id="90533-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="90533-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="90533-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="90533-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="90533-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="90533-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="90533-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="90533-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

