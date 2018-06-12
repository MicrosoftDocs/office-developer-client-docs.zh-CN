---
title: PidTagAlternateRecipientAllowed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAlternateRecipientAllowed
api_type:
- HeaderDef
ms.assetid: dbbdeb54-3d14-4601-a77b-55ee31f33416
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: dc77f9c7b58fc925048d6dec2bee2ff96a8723b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777316"
---
# <a name="pidtagalternaterecipientallowed-canonical-property"></a><span data-ttu-id="a36f8-103">PidTagAlternateRecipientAllowed 规范属性</span><span class="sxs-lookup"><span data-stu-id="a36f8-103">PidTagAlternateRecipientAllowed Canonical Property</span></span>

  
  
<span data-ttu-id="a36f8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a36f8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a36f8-105">包含 TRUE，如果发件人允许自动转接的此消息。</span><span class="sxs-lookup"><span data-stu-id="a36f8-105">Contains TRUE if the sender permits auto forwarding of this message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a36f8-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="a36f8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a36f8-107">PR_ALTERNATE_RECIPIENT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="a36f8-107">PR_ALTERNATE_RECIPIENT_ALLOWED</span></span>  <br/> |
|<span data-ttu-id="a36f8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a36f8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a36f8-109">0x0002</span><span class="sxs-lookup"><span data-stu-id="a36f8-109">0x0002</span></span>  <br/> |
|<span data-ttu-id="a36f8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a36f8-110">Data type:</span></span>  <br/> |<span data-ttu-id="a36f8-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="a36f8-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="a36f8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a36f8-112">Area:</span></span>  <br/> |<span data-ttu-id="a36f8-113">Address</span><span class="sxs-lookup"><span data-stu-id="a36f8-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a36f8-114">备注</span><span class="sxs-lookup"><span data-stu-id="a36f8-114">Remarks</span></span>

<span data-ttu-id="a36f8-115">如果不允许自动转接，或者如果已不指定任何备用收件人，应生成原件报告。</span><span class="sxs-lookup"><span data-stu-id="a36f8-115">If auto forwarding is not permitted or if no alternate recipient has been designated, a nondelivery report should be generated.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a36f8-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="a36f8-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a36f8-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="a36f8-117">Protocol specifications</span></span>

<span data-ttu-id="a36f8-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a36f8-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a36f8-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a36f8-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a36f8-120">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a36f8-120">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a36f8-121">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="a36f8-121">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="a36f8-122">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a36f8-122">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a36f8-123">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="a36f8-123">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="a36f8-124">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a36f8-124">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a36f8-125">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a36f8-125">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a36f8-126">头文件</span><span class="sxs-lookup"><span data-stu-id="a36f8-126">Header files</span></span>

<span data-ttu-id="a36f8-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a36f8-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="a36f8-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a36f8-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="a36f8-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a36f8-129">Mapitags.h</span></span>
  
> <span data-ttu-id="a36f8-130">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a36f8-130">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a36f8-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a36f8-131">See also</span></span>



[<span data-ttu-id="a36f8-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a36f8-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a36f8-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a36f8-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a36f8-134">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a36f8-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a36f8-135">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a36f8-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

