---
title: PidLidTaskFFixOffline 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskFFixOffline
api_type:
- COM
ms.assetid: bbaf7df4-2de0-4da3-9125-eb24dfa94cd8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b8da927fe0080a83748bbb2941979dcb246222fa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777085"
---
# <a name="pidlidtaskffixoffline-canonical-property"></a><span data-ttu-id="59e08-103">PidLidTaskFFixOffline 规范属性</span><span class="sxs-lookup"><span data-stu-id="59e08-103">PidLidTaskFFixOffline Canonical Property</span></span>

  
  
<span data-ttu-id="59e08-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="59e08-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59e08-105">指示**dispidTaskOwner** ([PidLidTaskOwner](pidlidtaskowner-canonical-property.md)) 属性的准确性。</span><span class="sxs-lookup"><span data-stu-id="59e08-105">Indicates the accuracy of the **dispidTaskOwner** ([PidLidTaskOwner](pidlidtaskowner-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="59e08-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="59e08-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="59e08-107">dispidTaskFFixOffline</span><span class="sxs-lookup"><span data-stu-id="59e08-107">dispidTaskFFixOffline</span></span>  <br/> |
|<span data-ttu-id="59e08-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="59e08-108">Property set:</span></span>  <br/> |<span data-ttu-id="59e08-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="59e08-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="59e08-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="59e08-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="59e08-111">0x0000812C</span><span class="sxs-lookup"><span data-stu-id="59e08-111">0x0000812C</span></span>  <br/> |
|<span data-ttu-id="59e08-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="59e08-112">Data type:</span></span>  <br/> |<span data-ttu-id="59e08-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="59e08-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="59e08-114">区域：</span><span class="sxs-lookup"><span data-stu-id="59e08-114">Area:</span></span>  <br/> |<span data-ttu-id="59e08-115">Task</span><span class="sxs-lookup"><span data-stu-id="59e08-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="59e08-116">说明</span><span class="sxs-lookup"><span data-stu-id="59e08-116">Remarks</span></span>

<span data-ttu-id="59e08-117">如果**dispidTaskFFixOffline**属性设置为 FALSE，或者是未设置，则**dispidTaskOwner**属性的值正确。</span><span class="sxs-lookup"><span data-stu-id="59e08-117">If the **dispidTaskFFixOffline** property is set to FALSE or is unset, the value for the **dispidTaskOwner** property is correct.</span></span> <span data-ttu-id="59e08-118">如果**dispidTaskFFixOffline**设置为 TRUE，客户端无法确定**dispidTaskOwner**准确值。</span><span class="sxs-lookup"><span data-stu-id="59e08-118">If **dispidTaskFFixOffline** is set to TRUE, the client cannot determine an accurate value for **dispidTaskOwner**.</span></span> <span data-ttu-id="59e08-119">在这种情况下，客户端可以将**dispidTaskOwner**设置为一个通用的所有者名称，例如"Unknown"。</span><span class="sxs-lookup"><span data-stu-id="59e08-119">In that case, the client can set **dispidTaskOwner** to a generic owner name, such as "Unknown".</span></span> <span data-ttu-id="59e08-120">但是，如果客户端遇到**dispidTaskFFixOffline**值为 TRUE，并且可以确定正确的所有者名称，客户端应更新**dispidTaskOwner**并**dispidTaskFFixOffline**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="59e08-120">However, if a client encounters a **dispidTaskFFixOffline** value of TRUE and can determine an accurate owner name, the client should update **dispidTaskOwner** and set **dispidTaskFFixOffline** to FALSE.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="59e08-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="59e08-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="59e08-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="59e08-122">Protocol specifications</span></span>

<span data-ttu-id="59e08-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59e08-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59e08-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="59e08-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="59e08-125">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59e08-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59e08-126">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="59e08-126">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span> 
    
### <a name="header-files"></a><span data-ttu-id="59e08-127">头文件</span><span class="sxs-lookup"><span data-stu-id="59e08-127">Header files</span></span>

<span data-ttu-id="59e08-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="59e08-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="59e08-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="59e08-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="59e08-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59e08-130">See also</span></span>



[<span data-ttu-id="59e08-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="59e08-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="59e08-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="59e08-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="59e08-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="59e08-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="59e08-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="59e08-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

