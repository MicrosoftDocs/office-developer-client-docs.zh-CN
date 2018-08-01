---
title: PidTagOriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayName
api_type:
- COM
ms.assetid: 176245d9-724d-44f1-b7a3-eddf652533b2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4a43bc33f13d8325a55d09b5ef3031dc632cf587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777928"
---
# <a name="pidtagoriginaldisplayname-canonical-property"></a><span data-ttu-id="d897e-103">PidTagOriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="d897e-103">PidTagOriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="d897e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d897e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d897e-105">包含通讯簿中复制到个人通讯簿或其他可写通讯簿条目的原始显示名称。</span><span class="sxs-lookup"><span data-stu-id="d897e-105">Contains the original display name for an entry copied from an address book to a personal address book or other writable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d897e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d897e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d897e-107">PR_ORIGINAL_DISPLAY_NAME，PR_ORIGINAL_DISPLAY_NAME_A，PR_ORIGINAL_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="d897e-107">PR_ORIGINAL_DISPLAY_NAME, PR_ORIGINAL_DISPLAY_NAME_A, PR_ORIGINAL_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="d897e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d897e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d897e-109">0x3A13</span><span class="sxs-lookup"><span data-stu-id="d897e-109">0x3A13</span></span>  <br/> |
|<span data-ttu-id="d897e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d897e-110">Data type:</span></span>  <br/> |<span data-ttu-id="d897e-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d897e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d897e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d897e-112">Area:</span></span>  <br/> |<span data-ttu-id="d897e-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="d897e-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d897e-114">说明</span><span class="sxs-lookup"><span data-stu-id="d897e-114">Remarks</span></span>

<span data-ttu-id="d897e-115">这些属性包含有关复制条目的原始源的信息。</span><span class="sxs-lookup"><span data-stu-id="d897e-115">These properties contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="d897e-116">对于 nonread 报表，这些属性包含一份在为其生成报告的原始邮件收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d897e-116">For a nonread report, these properties contain a copy of the display name of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="d897e-117">原始收件人是通讯组列表的一部分，当报表保留通讯组列表的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d897e-117">When the original recipient is part of a distribution list, the display name of the distribution list is preserved for the report.</span></span>
  
<span data-ttu-id="d897e-118">客户端应用程序可以使用这些属性，提供要比较的显示名称原封不动的副本，从而防止篡改或"欺骗"的项。</span><span class="sxs-lookup"><span data-stu-id="d897e-118">A client application can use these properties to prevent alteration or "spoofing" of entries, by giving an unaltered copy of the display name to compare.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d897e-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="d897e-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d897e-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="d897e-120">Protocol specifications</span></span>

<span data-ttu-id="d897e-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d897e-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d897e-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d897e-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d897e-123">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d897e-123">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d897e-124">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="d897e-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d897e-125">头文件</span><span class="sxs-lookup"><span data-stu-id="d897e-125">Header files</span></span>

<span data-ttu-id="d897e-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d897e-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="d897e-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d897e-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="d897e-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d897e-128">Mapitags.h</span></span>
  
> <span data-ttu-id="d897e-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d897e-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d897e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d897e-130">See also</span></span>



[<span data-ttu-id="d897e-131">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="d897e-131">PidTagTransmittableDisplayName Canonical Property</span></span>](pidtagtransmittabledisplayname-canonical-property.md)


[<span data-ttu-id="d897e-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d897e-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d897e-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d897e-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d897e-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d897e-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d897e-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d897e-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

