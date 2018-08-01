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
ms.openlocfilehash: d60531b087d00ca63a060a4dbfac559ba3b01788
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777944"
---
# <a name="pidtagoriginalentryid-canonical-property"></a><span data-ttu-id="bf6af-103">PidTagOriginalEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf6af-103">PidTagOriginalEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="bf6af-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bf6af-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bf6af-105">包含复制到个人通讯簿通讯簿或其他写通讯簿条目的原始项标识符。</span><span class="sxs-lookup"><span data-stu-id="bf6af-105">Contains the original entry identifier for an entry copied from an address book to a personal address book or other writeable address book.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bf6af-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bf6af-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bf6af-107">PR_ORIGINAL_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="bf6af-107">PR_ORIGINAL_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="bf6af-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="bf6af-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bf6af-109">0x3A12</span><span class="sxs-lookup"><span data-stu-id="bf6af-109">0x3A12</span></span>  <br/> |
|<span data-ttu-id="bf6af-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bf6af-110">Data type:</span></span>  <br/> |<span data-ttu-id="bf6af-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="bf6af-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="bf6af-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bf6af-112">Area:</span></span>  <br/> |<span data-ttu-id="bf6af-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="bf6af-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bf6af-114">说明</span><span class="sxs-lookup"><span data-stu-id="bf6af-114">Remarks</span></span>

<span data-ttu-id="bf6af-115">此属性是包含有关复制条目的原始源的信息的属性之一。</span><span class="sxs-lookup"><span data-stu-id="bf6af-115">This property is one of the properties that contain information about the original source of a copied entry.</span></span>
  
<span data-ttu-id="bf6af-116">对于 nonread 报表，此属性包含一份在为其生成报告的原始邮件收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="bf6af-116">For a nonread report, this property contains a copy of the entry identifier of the original message recipient for which the report is generated.</span></span> <span data-ttu-id="bf6af-117">原始收件人是通讯组列表的一部分，当报表保留通讯组列表的项标识符。</span><span class="sxs-lookup"><span data-stu-id="bf6af-117">When the original recipient is part of a distribution list, the entry identifier of the distribution list is preserved for the report.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bf6af-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="bf6af-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bf6af-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="bf6af-119">Protocol specifications</span></span>

<span data-ttu-id="bf6af-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bf6af-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bf6af-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="bf6af-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bf6af-122">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bf6af-122">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bf6af-123">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="bf6af-123">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="bf6af-124">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bf6af-124">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bf6af-125">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="bf6af-125">Handles synchronizing messaging object data between a server and a client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bf6af-126">头文件</span><span class="sxs-lookup"><span data-stu-id="bf6af-126">Header files</span></span>

<span data-ttu-id="bf6af-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bf6af-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="bf6af-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bf6af-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="bf6af-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bf6af-129">Mapitags.h</span></span>
  
> <span data-ttu-id="bf6af-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bf6af-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bf6af-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf6af-131">See also</span></span>



[<span data-ttu-id="bf6af-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bf6af-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bf6af-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bf6af-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bf6af-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bf6af-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bf6af-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bf6af-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

