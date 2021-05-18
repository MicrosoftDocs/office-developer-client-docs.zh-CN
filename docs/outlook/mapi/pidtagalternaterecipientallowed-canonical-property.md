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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0faeb12ee54ec5d1c584bacd51590b157035f4fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327984"
---
# <a name="pidtagalternaterecipientallowed-canonical-property"></a><span data-ttu-id="d354f-103">PidTagAlternateRecipientAllowed 规范属性</span><span class="sxs-lookup"><span data-stu-id="d354f-103">PidTagAlternateRecipientAllowed Canonical Property</span></span>

  
  
<span data-ttu-id="d354f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d354f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d354f-105">如果发件人允许自动转发此邮件，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="d354f-105">Contains TRUE if the sender permits auto forwarding of this message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d354f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d354f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d354f-107">PR_ALTERNATE_RECIPIENT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="d354f-107">PR_ALTERNATE_RECIPIENT_ALLOWED</span></span>  <br/> |
|<span data-ttu-id="d354f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d354f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d354f-109">0x0002</span><span class="sxs-lookup"><span data-stu-id="d354f-109">0x0002</span></span>  <br/> |
|<span data-ttu-id="d354f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d354f-110">Data type:</span></span>  <br/> |<span data-ttu-id="d354f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="d354f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="d354f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d354f-112">Area:</span></span>  <br/> |<span data-ttu-id="d354f-113">地址</span><span class="sxs-lookup"><span data-stu-id="d354f-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d354f-114">备注</span><span class="sxs-lookup"><span data-stu-id="d354f-114">Remarks</span></span>

<span data-ttu-id="d354f-115">如果不允许自动转发或尚未指定备用收件人，应生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="d354f-115">If auto forwarding is not permitted or if no alternate recipient has been designated, a nondelivery report should be generated.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d354f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="d354f-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d354f-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d354f-117">Protocol specifications</span></span>

<span data-ttu-id="d354f-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d354f-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d354f-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d354f-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d354f-120">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d354f-120">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d354f-121">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="d354f-121">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="d354f-122">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d354f-122">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d354f-123">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="d354f-123">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="d354f-124">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d354f-124">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d354f-125">将邮件和附件对象编码和解码为有效的流表示形式。</span><span class="sxs-lookup"><span data-stu-id="d354f-125">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d354f-126">头文件</span><span class="sxs-lookup"><span data-stu-id="d354f-126">Header files</span></span>

<span data-ttu-id="d354f-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d354f-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="d354f-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d354f-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="d354f-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d354f-129">Mapitags.h</span></span>
  
> <span data-ttu-id="d354f-130">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d354f-130">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d354f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d354f-131">See also</span></span>



[<span data-ttu-id="d354f-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d354f-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d354f-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d354f-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d354f-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d354f-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d354f-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d354f-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

