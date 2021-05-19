---
title: PidLidTaskOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOrdinal
api_type:
- COM
ms.assetid: 1021860e-4c40-4c22-aa68-b568d046aaf7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a64008da93584529916a9303176bba0aa08d3fac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357958"
---
# <a name="pidlidtaskordinal-canonical-property"></a><span data-ttu-id="38b82-103">PidLidTaskOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="38b82-103">PidLidTaskOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="38b82-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38b82-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38b82-105">帮助执行自定义排序任务。</span><span class="sxs-lookup"><span data-stu-id="38b82-105">Provides an aid to custom sorting tasks.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="38b82-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="38b82-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="38b82-107">dispidTaskOrdinal</span><span class="sxs-lookup"><span data-stu-id="38b82-107">dispidTaskOrdinal</span></span>  <br/> |
|<span data-ttu-id="38b82-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="38b82-108">Property set:</span></span>  <br/> |<span data-ttu-id="38b82-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="38b82-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="38b82-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="38b82-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="38b82-111">0x00008123</span><span class="sxs-lookup"><span data-stu-id="38b82-111">0x00008123</span></span>  <br/> |
|<span data-ttu-id="38b82-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="38b82-112">Data type:</span></span>  <br/> |<span data-ttu-id="38b82-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="38b82-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="38b82-114">区域：</span><span class="sxs-lookup"><span data-stu-id="38b82-114">Area:</span></span>  <br/> |<span data-ttu-id="38b82-115">任务</span><span class="sxs-lookup"><span data-stu-id="38b82-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38b82-116">备注</span><span class="sxs-lookup"><span data-stu-id="38b82-116">Remarks</span></span>

<span data-ttu-id="38b82-117">此属性可能未设置。</span><span class="sxs-lookup"><span data-stu-id="38b82-117">This property may be left unset.</span></span> <span data-ttu-id="38b82-118">如果设置，则其值必须大于"0x800186A0" (-2，147，383，648) 且小于"0x7FFE7960" (2，147，383，648) 并且在同一文件夹中的任务之间必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="38b82-118">If set, its value must be greater than "0x800186A0" (-2,147,383,648) and less than "0x7FFE7960" (2,147,383,648) and must be unique among tasks in the same folder.</span></span>
  
<span data-ttu-id="38b82-119">每当客户端将此属性设置为小于文件夹的 **PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) 属性的当前值的负数时，客户端还必须更新文件夹上的 **PR_ORDINAL_MOST。**</span><span class="sxs-lookup"><span data-stu-id="38b82-119">Whenever the client sets this property to a number less than the negative of the current value of the **PR_ORDINAL_MOST** ([PidTagOrdinalMost](pidtagordinalmost-canonical-property.md)) property of the folder, the client must also update **PR_ORDINAL_MOST** on the folder.</span></span> 
  
<span data-ttu-id="38b82-120">文件夹 **PR_ORDINAL_MOST** 属性提供了一种有效方法，可确定同一文件夹中的任务之间的唯一值。</span><span class="sxs-lookup"><span data-stu-id="38b82-120">The **PR_ORDINAL_MOST** property of the folder provides an efficient way to determine a unique value among tasks in the same folder.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="38b82-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="38b82-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="38b82-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="38b82-122">Protocol specifications</span></span>

<span data-ttu-id="38b82-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38b82-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38b82-124">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="38b82-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="38b82-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38b82-125">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38b82-126">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="38b82-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="38b82-127">头文件</span><span class="sxs-lookup"><span data-stu-id="38b82-127">Header files</span></span>

<span data-ttu-id="38b82-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="38b82-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="38b82-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="38b82-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38b82-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38b82-130">See also</span></span>



[<span data-ttu-id="38b82-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="38b82-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="38b82-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="38b82-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="38b82-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="38b82-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="38b82-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="38b82-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

