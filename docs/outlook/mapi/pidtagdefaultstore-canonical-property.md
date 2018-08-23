---
title: PidTagDefaultStore 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultStore
api_type:
- HeaderDef
ms.assetid: 6314d91c-4948-4fd1-bacc-932d4bb2c22f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d544c741685d401aaf36fe19be50ab402c9e5604
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592680"
---
# <a name="pidtagdefaultstore-canonical-property"></a><span data-ttu-id="6a2b2-103">PidTagDefaultStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a2b2-103">PidTagDefaultStore Canonical Property</span></span>

  
  
<span data-ttu-id="6a2b2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a2b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a2b2-105">如果消息存储为默认的邮件存储消息存储表中，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-105">Contains TRUE if a message store is the default message store in the message store table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6a2b2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a2b2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a2b2-107">PR_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="6a2b2-107">PR_DEFAULT_STORE</span></span>  <br/> |
|<span data-ttu-id="6a2b2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6a2b2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a2b2-109">0x3400</span><span class="sxs-lookup"><span data-stu-id="6a2b2-109">0x3400</span></span>  <br/> |
|<span data-ttu-id="6a2b2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a2b2-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a2b2-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6a2b2-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6a2b2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a2b2-112">Area:</span></span>  <br/> |<span data-ttu-id="6a2b2-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="6a2b2-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a2b2-114">注解</span><span class="sxs-lookup"><span data-stu-id="6a2b2-114">Remarks</span></span>

<span data-ttu-id="6a2b2-115">此属性显示为消息存储表中的列。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-115">This property appears as a column in the message store table.</span></span> <span data-ttu-id="6a2b2-116">值基于**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-116">The value is based on **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6a2b2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a2b2-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6a2b2-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="6a2b2-118">Protocol specifications</span></span>

<span data-ttu-id="6a2b2-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a2b2-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a2b2-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6a2b2-121">头文件</span><span class="sxs-lookup"><span data-stu-id="6a2b2-121">Header files</span></span>

<span data-ttu-id="6a2b2-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6a2b2-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a2b2-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a2b2-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6a2b2-124">Mapitags.h</span></span>
  
> <span data-ttu-id="6a2b2-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a2b2-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a2b2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a2b2-126">See also</span></span>



[<span data-ttu-id="6a2b2-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a2b2-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a2b2-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a2b2-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a2b2-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a2b2-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a2b2-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a2b2-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

