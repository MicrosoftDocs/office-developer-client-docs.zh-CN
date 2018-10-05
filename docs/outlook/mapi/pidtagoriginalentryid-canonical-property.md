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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391032"
---
# <a name="pidtagoriginalentryid-canonical-property"></a><span data-ttu-id="0922b-103">PidTagOriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="0922b-103">PidTagOriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="0922b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0922b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0922b-105">包含复制到个人通讯簿通讯簿或其他写通讯簿条目的原始项标识符。</span><span class="sxs-lookup"><span data-stu-id="0922b-105">Contains the original entry identifier for an entry copied from an address book to a personal address book or other writeable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0922b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0922b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0922b-107">PR_ORIGINAL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="0922b-107">PR_ORIGINAL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="0922b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0922b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0922b-109">0x3A12</span><span class="sxs-lookup"><span data-stu-id="0922b-109">0x3A12</span></span>  <br/> |
|<span data-ttu-id="0922b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0922b-110">Data type:</span></span>  <br/> |<span data-ttu-id="0922b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0922b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0922b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0922b-112">Area:</span></span>  <br/> |<span data-ttu-id="0922b-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="0922b-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0922b-114">说明</span><span class="sxs-lookup"><span data-stu-id="0922b-114">Remarks</span></span>

<span data-ttu-id="0922b-115">此属性是包含有关复制条目的原始源的信息的属性之一。</span><span class="sxs-lookup"><span data-stu-id="0922b-115">This property is one of the properties that contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="0922b-116">对于 nonread 报表，此属性包含一份在为其生成报告的原始邮件收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0922b-116">For a nonread report, this property contains a copy of the entry identifier of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="0922b-117">原始收件人是通讯组列表的一部分，当报表保留通讯组列表的项标识符。</span><span class="sxs-lookup"><span data-stu-id="0922b-117">When the original recipient is part of a distribution list, the entry identifier of the distribution list is preserved for the report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0922b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="0922b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0922b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="0922b-119">Protocol specifications</span></span>

<span data-ttu-id="0922b-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0922b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0922b-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="0922b-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0922b-122">[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0922b-122">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0922b-123">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="0922b-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="0922b-124">[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0922b-124">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0922b-125">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="0922b-125">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0922b-126">头文件</span><span class="sxs-lookup"><span data-stu-id="0922b-126">Header files</span></span>

<span data-ttu-id="0922b-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0922b-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="0922b-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0922b-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="0922b-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0922b-129">Mapitags.h</span></span>
  
> <span data-ttu-id="0922b-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0922b-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0922b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0922b-131">See also</span></span>



[<span data-ttu-id="0922b-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0922b-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0922b-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0922b-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0922b-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0922b-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0922b-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0922b-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

