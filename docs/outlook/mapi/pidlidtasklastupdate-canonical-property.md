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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391379"
---
# <a name="pidlidtasklastupdate-canonical-property"></a><span data-ttu-id="9b782-103">PidLidTaskLastUpdate 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b782-103">PidLidTaskLastUpdate Canonical Property</span></span>

  
  
<span data-ttu-id="9b782-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b782-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b782-105">指示的协调世界时 (UTC) 和日期已对任务进行且由**dispidTaskHistory** ([PidLidTaskHistory](pidlidtasklastupdate-canonical-property.md)) 属性的最新更改。</span><span class="sxs-lookup"><span data-stu-id="9b782-105">Indicates the Coordinated Universal Time (UTC) and date of the most recent change that was made to the task and indicated by the **dispidTaskHistory** ([PidLidTaskHistory](pidlidtasklastupdate-canonical-property.md)) property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9b782-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9b782-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9b782-107">dispidTaskLastUpdate</span><span class="sxs-lookup"><span data-stu-id="9b782-107">dispidTaskLastUpdate</span></span>  <br/> |
|<span data-ttu-id="9b782-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="9b782-108">Property set:</span></span>  <br/> |<span data-ttu-id="9b782-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="9b782-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="9b782-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="9b782-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="9b782-111">0x00008115</span><span class="sxs-lookup"><span data-stu-id="9b782-111">0x00008115</span></span>  <br/> |
|<span data-ttu-id="9b782-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9b782-112">Data type:</span></span>  <br/> |<span data-ttu-id="9b782-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="9b782-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="9b782-114">区域：</span><span class="sxs-lookup"><span data-stu-id="9b782-114">Area:</span></span>  <br/> |<span data-ttu-id="9b782-115">Task</span><span class="sxs-lookup"><span data-stu-id="9b782-115">Task</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="9b782-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="9b782-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9b782-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="9b782-117">Protocol specifications</span></span>

<span data-ttu-id="9b782-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9b782-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9b782-119">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9b782-119">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9b782-120">[[MS OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9b782-120">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9b782-121">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="9b782-121">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9b782-122">头文件</span><span class="sxs-lookup"><span data-stu-id="9b782-122">Header files</span></span>

<span data-ttu-id="9b782-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9b782-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="9b782-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9b782-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9b782-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b782-125">See also</span></span>



[<span data-ttu-id="9b782-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9b782-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9b782-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9b782-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9b782-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9b782-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9b782-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9b782-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

