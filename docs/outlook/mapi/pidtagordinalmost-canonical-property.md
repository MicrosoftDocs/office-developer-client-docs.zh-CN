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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 31f39cfbd0e993bfc28003fd64e8af97e7e76818
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329185"
---
# <a name="pidtagordinalmost-canonical-property"></a><span data-ttu-id="4a0bb-103">PidTagOrdinalMost 规范属性</span><span class="sxs-lookup"><span data-stu-id="4a0bb-103">PidTagOrdinalMost Canonical Property</span></span>

  
  
<span data-ttu-id="4a0bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a0bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a0bb-105">包含一个正数, 其负值小于或等于文件夹中所有任务的**dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-105">Contains a positive number whose negative is less than or equal to the value of the **dispidTaskOrdinal** ([PidLidTaskOrdinal](pidlidtaskordinal-canonical-property.md)) property of all tasks in the folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4a0bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4a0bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4a0bb-107">PR_ORDINAL_MOST</span><span class="sxs-lookup"><span data-stu-id="4a0bb-107">PR_ORDINAL_MOST</span></span>  <br/> |
|<span data-ttu-id="4a0bb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4a0bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4a0bb-109">0x36E2</span><span class="sxs-lookup"><span data-stu-id="4a0bb-109">0x36E2</span></span>  <br/> |
|<span data-ttu-id="4a0bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4a0bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="4a0bb-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4a0bb-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4a0bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4a0bb-112">Area:</span></span>  <br/> |<span data-ttu-id="4a0bb-113">任务</span><span class="sxs-lookup"><span data-stu-id="4a0bb-113">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4a0bb-114">注解</span><span class="sxs-lookup"><span data-stu-id="4a0bb-114">Remarks</span></span>

<span data-ttu-id="4a0bb-115">当文件夹中任何 task 对象的**dispidTaskOrdinal**属性更改为违反条件的方式时, 必须更新此属性以保持此条件。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-115">This property must be updated to maintain this condition whenever the **dispidTaskOrdinal** property of any task object in the folder changes in a way that would violate the condition.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4a0bb-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="4a0bb-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4a0bb-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="4a0bb-117">Protocol specifications</span></span>

<span data-ttu-id="4a0bb-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a0bb-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4a0bb-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4a0bb-120">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a0bb-120">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4a0bb-121">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
  
### <a name="header-files"></a><span data-ttu-id="4a0bb-122">头文件</span><span class="sxs-lookup"><span data-stu-id="4a0bb-122">Header files</span></span>

<span data-ttu-id="4a0bb-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4a0bb-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="4a0bb-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="4a0bb-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4a0bb-125">Mapitags.h</span></span>
  
> <span data-ttu-id="4a0bb-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4a0bb-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4a0bb-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a0bb-127">See also</span></span>



[<span data-ttu-id="4a0bb-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4a0bb-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4a0bb-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4a0bb-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4a0bb-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4a0bb-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4a0bb-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4a0bb-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

