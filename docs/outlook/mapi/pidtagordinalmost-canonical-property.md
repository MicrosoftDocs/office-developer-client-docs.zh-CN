---
title: PidTagOrdinalMost 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOrdinalMost
api_type:
- COM
ms.assetid: c18de08b-8c28-4cdf-bd2e-b9c650cd6da6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0c2cf784ff9a86c9e2a2ce1a25b3c4b8ff7d8b75
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777909"
---
# <a name="pidtagordinalmost-canonical-property"></a><span data-ttu-id="78cc4-103">PidTagOrdinalMost 规范属性</span><span class="sxs-lookup"><span data-stu-id="78cc4-103">PidTagOrdinalMost Canonical Property</span></span>

  
  
<span data-ttu-id="78cc4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="78cc4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="78cc4-105">包含的正数其负小于或等于文件夹中的所有任务的**dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="78cc4-105">Contains a positive number whose negative is less than or equal to the value of the **dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) property of all tasks in the folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="78cc4-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="78cc4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="78cc4-107">PR_ORDINAL_MOST</span><span class="sxs-lookup"><span data-stu-id="78cc4-107">PR_ORDINAL_MOST</span></span>  <br/> |
|<span data-ttu-id="78cc4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="78cc4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="78cc4-109">0x36E2</span><span class="sxs-lookup"><span data-stu-id="78cc4-109">0x36E2</span></span>  <br/> |
|<span data-ttu-id="78cc4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="78cc4-110">Data type:</span></span>  <br/> |<span data-ttu-id="78cc4-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="78cc4-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="78cc4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="78cc4-112">Area:</span></span>  <br/> |<span data-ttu-id="78cc4-113">任务</span><span class="sxs-lookup"><span data-stu-id="78cc4-113">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="78cc4-114">备注</span><span class="sxs-lookup"><span data-stu-id="78cc4-114">Remarks</span></span>

<span data-ttu-id="78cc4-115">此属性必须更新维护这种情况，只要文件夹中的任何任务对象的**dispidTaskOrdinal**属性更改冲突条件的方式。</span><span class="sxs-lookup"><span data-stu-id="78cc4-115">This property must be updated to maintain this condition whenever the **dispidTaskOrdinal** property of any task object in the folder changes in a way that would violate the condition.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="78cc4-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="78cc4-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="78cc4-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="78cc4-117">Protocol specifications</span></span>

<span data-ttu-id="78cc4-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="78cc4-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="78cc4-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="78cc4-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="78cc4-120">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="78cc4-120">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="78cc4-121">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="78cc4-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
  
### <a name="header-files"></a><span data-ttu-id="78cc4-122">头文件</span><span class="sxs-lookup"><span data-stu-id="78cc4-122">Header files</span></span>

<span data-ttu-id="78cc4-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="78cc4-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="78cc4-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="78cc4-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="78cc4-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="78cc4-125">Mapitags.h</span></span>
  
> <span data-ttu-id="78cc4-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="78cc4-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="78cc4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78cc4-127">See also</span></span>



[<span data-ttu-id="78cc4-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="78cc4-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="78cc4-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="78cc4-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="78cc4-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="78cc4-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="78cc4-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="78cc4-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

