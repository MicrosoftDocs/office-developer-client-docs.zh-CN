---
title: PidLidTaskLastUpdate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastUpdate
api_type:
- COM
ms.assetid: 65b73d0f-f1f1-4c11-8834-f7c736a30ffc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95af98acad6b2aa4bc95ea5e6478e6ca21c8eb8f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356831"
---
# <a name="pidlidtasklastupdate-canonical-property"></a><span data-ttu-id="d1603-103">PidLidTaskLastUpdate 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1603-103">PidLidTaskLastUpdate Canonical Property</span></span>

  
  
<span data-ttu-id="d1603-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1603-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1603-105">指示对任务所做的最新更改的协调世界时 (UTC) 和日期, 由**dispidTaskHistory** ([PidLidTaskHistory](pidlidtasklastupdate-canonical-property.md)) 属性指示。</span><span class="sxs-lookup"><span data-stu-id="d1603-105">Indicates the Coordinated Universal Time (UTC) and date of the most recent change that was made to the task and indicated by the **dispidTaskHistory** ([PidLidTaskHistory](pidlidtasklastupdate-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1603-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d1603-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1603-107">dispidTaskLastUpdate</span><span class="sxs-lookup"><span data-stu-id="d1603-107">dispidTaskLastUpdate</span></span>  <br/> |
|<span data-ttu-id="d1603-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="d1603-108">Property set:</span></span>  <br/> |<span data-ttu-id="d1603-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="d1603-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="d1603-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="d1603-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d1603-111">0x00008115</span><span class="sxs-lookup"><span data-stu-id="d1603-111">0x00008115</span></span>  <br/> |
|<span data-ttu-id="d1603-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1603-112">Data type:</span></span>  <br/> |<span data-ttu-id="d1603-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d1603-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="d1603-114">区域：</span><span class="sxs-lookup"><span data-stu-id="d1603-114">Area:</span></span>  <br/> |<span data-ttu-id="d1603-115">任务</span><span class="sxs-lookup"><span data-stu-id="d1603-115">Task</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d1603-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1603-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d1603-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="d1603-117">Protocol specifications</span></span>

<span data-ttu-id="d1603-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1603-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1603-119">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d1603-119">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d1603-120">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1603-120">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1603-121">定义为任务、任务分配和任务更新的电子等效项建模的多个对象。</span><span class="sxs-lookup"><span data-stu-id="d1603-121">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d1603-122">头文件</span><span class="sxs-lookup"><span data-stu-id="d1603-122">Header files</span></span>

<span data-ttu-id="d1603-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d1603-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1603-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1603-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1603-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1603-125">See also</span></span>



[<span data-ttu-id="d1603-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1603-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1603-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1603-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1603-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d1603-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1603-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1603-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

