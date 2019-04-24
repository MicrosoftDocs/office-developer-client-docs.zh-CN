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
ms.openlocfilehash: 2b7aef416beb9eee70aeff8cf20cb38ae8e7993f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355473"
---
# <a name="pidtagoriginaldisplayname-canonical-property"></a><span data-ttu-id="e8482-103">PidTagOriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8482-103">PidTagOriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="e8482-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8482-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8482-105">包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始显示名称。</span><span class="sxs-lookup"><span data-stu-id="e8482-105">Contains the original display name for an entry copied from an address book to a personal address book or other writable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e8482-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e8482-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e8482-107">PR_ORIGINAL_DISPLAY_NAME、PR_ORIGINAL_DISPLAY_NAME_A、PR_ORIGINAL_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="e8482-107">PR_ORIGINAL_DISPLAY_NAME, PR_ORIGINAL_DISPLAY_NAME_A, PR_ORIGINAL_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="e8482-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e8482-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e8482-109">0x3A13</span><span class="sxs-lookup"><span data-stu-id="e8482-109">0x3A13</span></span>  <br/> |
|<span data-ttu-id="e8482-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e8482-110">Data type:</span></span>  <br/> |<span data-ttu-id="e8482-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e8482-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e8482-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e8482-112">Area:</span></span>  <br/> |<span data-ttu-id="e8482-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="e8482-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e8482-114">注解</span><span class="sxs-lookup"><span data-stu-id="e8482-114">Remarks</span></span>

<span data-ttu-id="e8482-115">这些属性包含有关复制的条目的原始源的信息。</span><span class="sxs-lookup"><span data-stu-id="e8482-115">These properties contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="e8482-116">对于未读报告, 这些属性包含为其生成报告的原始邮件收件人的显示名称的副本。</span><span class="sxs-lookup"><span data-stu-id="e8482-116">For a nonread report, these properties contain a copy of the display name of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="e8482-117">当原始收件人是通讯组列表的一部分时, 将为该报告保留通讯组列表的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e8482-117">When the original recipient is part of a distribution list, the display name of the distribution list is preserved for the report.</span></span>
  
<span data-ttu-id="e8482-118">客户端应用程序可以使用这些属性来阻止对条目的更改或 "欺骗", 方法是提供要比较的未更改的显示名称副本。</span><span class="sxs-lookup"><span data-stu-id="e8482-118">A client application can use these properties to prevent alteration or "spoofing" of entries, by giving an unaltered copy of the display name to compare.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e8482-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e8482-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e8482-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="e8482-120">Protocol specifications</span></span>

<span data-ttu-id="e8482-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8482-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e8482-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e8482-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e8482-123">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e8482-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e8482-124">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e8482-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e8482-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e8482-125">Header files</span></span>

<span data-ttu-id="e8482-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e8482-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e8482-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e8482-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="e8482-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="e8482-128">Mapitags.h</span></span>
  
> <span data-ttu-id="e8482-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e8482-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e8482-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8482-130">See also</span></span>



[<span data-ttu-id="e8482-131">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8482-131">PidTagTransmittableDisplayName Canonical Property</span></span>](pidtagtransmittabledisplayname-canonical-property.md)


[<span data-ttu-id="e8482-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e8482-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e8482-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8482-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e8482-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e8482-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e8482-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e8482-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

