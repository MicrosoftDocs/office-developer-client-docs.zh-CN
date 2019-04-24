---
title: PidTagOriginalEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalEntryId
api_type:
- COM
ms.assetid: 8197d2c7-8665-41b8-bd3a-e9c1c2e642e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f3f4f42d91c4091943d6183508e2bc76c17197fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342719"
---
# <a name="pidtagoriginalentryid-canonical-property"></a><span data-ttu-id="7c54c-103">PidTagOriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="7c54c-103">PidTagOriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="7c54c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c54c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c54c-105">包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7c54c-105">Contains the original entry identifier for an entry copied from an address book to a personal address book or other writeable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7c54c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7c54c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7c54c-107">PR_ORIGINAL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="7c54c-107">PR_ORIGINAL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="7c54c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7c54c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7c54c-109">0x3A12</span><span class="sxs-lookup"><span data-stu-id="7c54c-109">0x3A12</span></span>  <br/> |
|<span data-ttu-id="7c54c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7c54c-110">Data type:</span></span>  <br/> |<span data-ttu-id="7c54c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7c54c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7c54c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7c54c-112">Area:</span></span>  <br/> |<span data-ttu-id="7c54c-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="7c54c-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7c54c-114">注解</span><span class="sxs-lookup"><span data-stu-id="7c54c-114">Remarks</span></span>

<span data-ttu-id="7c54c-115">此属性是包含有关复制的条目的原始源的信息的属性之一。</span><span class="sxs-lookup"><span data-stu-id="7c54c-115">This property is one of the properties that contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="7c54c-116">对于未读报告, 此属性包含为其生成报告的原始邮件收件人的条目标识符的副本。</span><span class="sxs-lookup"><span data-stu-id="7c54c-116">For a nonread report, this property contains a copy of the entry identifier of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="7c54c-117">当原始收件人是通讯组列表的一部分时, 将为该报告保留通讯组列表的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7c54c-117">When the original recipient is part of a distribution list, the entry identifier of the distribution list is preserved for the report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7c54c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7c54c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7c54c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7c54c-119">Protocol specifications</span></span>

<span data-ttu-id="7c54c-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c54c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7c54c-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7c54c-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7c54c-122">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c54c-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7c54c-123">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7c54c-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="7c54c-124">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7c54c-124">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7c54c-125">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="7c54c-125">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7c54c-126">头文件</span><span class="sxs-lookup"><span data-stu-id="7c54c-126">Header files</span></span>

<span data-ttu-id="7c54c-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7c54c-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="7c54c-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7c54c-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="7c54c-129">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7c54c-129">Mapitags.h</span></span>
  
> <span data-ttu-id="7c54c-130">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7c54c-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7c54c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c54c-131">See also</span></span>



[<span data-ttu-id="7c54c-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7c54c-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7c54c-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7c54c-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7c54c-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7c54c-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7c54c-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7c54c-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

