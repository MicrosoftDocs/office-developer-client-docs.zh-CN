---
title: PidTagOriginalSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSearchKey
api_type:
- COM
ms.assetid: ac5eb91d-31c9-459b-bb22-f4ccfc92d1db
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 26854b640669bbc6479ce90ba9cad18cdf4d9264
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777966"
---
# <a name="pidtagoriginalsearchkey-canonical-property"></a><span data-ttu-id="8911a-103">PidTagOriginalSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="8911a-103">PidTagOriginalSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="8911a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8911a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8911a-105">包含原始搜索密钥复制到个人通讯簿通讯簿或其他写通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="8911a-105">Contains the original search key for an entry copied from an address book to a personal address book or other writeable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8911a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8911a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8911a-107">PR_ORIGINAL_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="8911a-107">PR_ORIGINAL_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="8911a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8911a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8911a-109">0x3A14</span><span class="sxs-lookup"><span data-stu-id="8911a-109">0x3A14</span></span>  <br/> |
|<span data-ttu-id="8911a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8911a-110">Data type:</span></span>  <br/> |<span data-ttu-id="8911a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8911a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8911a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8911a-112">Area:</span></span>  <br/> |<span data-ttu-id="8911a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="8911a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8911a-114">说明</span><span class="sxs-lookup"><span data-stu-id="8911a-114">Remarks</span></span>

<span data-ttu-id="8911a-115">此属性是包含有关复制条目的原始源的信息的属性之一。</span><span class="sxs-lookup"><span data-stu-id="8911a-115">This property is one of the properties that contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="8911a-116">对于 nonread 报表，此属性包含搜索关键字的原始邮件收件人为其生成报告的副本。</span><span class="sxs-lookup"><span data-stu-id="8911a-116">For a nonread report, this property contains a copy of the search key of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="8911a-117">原始收件人是通讯组列表的一部分，当报表保留通讯组列表的搜索键。</span><span class="sxs-lookup"><span data-stu-id="8911a-117">When the original recipient is part of a distribution list, the search key of the distribution list is preserved for the report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8911a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="8911a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8911a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="8911a-119">Protocol specifications</span></span>

<span data-ttu-id="8911a-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8911a-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8911a-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="8911a-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8911a-122">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8911a-122">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8911a-123">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="8911a-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8911a-124">头文件</span><span class="sxs-lookup"><span data-stu-id="8911a-124">Header files</span></span>

<span data-ttu-id="8911a-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8911a-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="8911a-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8911a-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="8911a-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8911a-127">Mapitags.h</span></span>
  
> <span data-ttu-id="8911a-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8911a-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8911a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8911a-129">See also</span></span>



[<span data-ttu-id="8911a-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8911a-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8911a-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8911a-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8911a-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8911a-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8911a-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8911a-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

