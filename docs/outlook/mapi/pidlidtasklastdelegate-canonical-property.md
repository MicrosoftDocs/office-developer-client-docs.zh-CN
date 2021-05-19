---
title: PidLidTaskLastDelegate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastDelegate
api_type:
- COM
ms.assetid: 5eb8c1ce-063f-4273-acba-e6f9c994e7d3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ddf4b81ed35f500dad0029ea6375e9a75a996186
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355669"
---
# <a name="pidlidtasklastdelegate-canonical-property"></a><span data-ttu-id="12164-103">PidLidTaskLastDelegate 规范属性</span><span class="sxs-lookup"><span data-stu-id="12164-103">PidLidTaskLastDelegate Canonical Property</span></span>

  
  
<span data-ttu-id="12164-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12164-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="12164-105">命名最近分配或分配了该任务的用户。</span><span class="sxs-lookup"><span data-stu-id="12164-105">Names the user who most recently assigned or was assigned the task.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12164-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12164-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="12164-107">dispidTaskLastDelegate</span><span class="sxs-lookup"><span data-stu-id="12164-107">dispidTaskLastDelegate</span></span>  <br/> |
|<span data-ttu-id="12164-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="12164-108">Property set:</span></span>  <br/> |<span data-ttu-id="12164-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="12164-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="12164-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="12164-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="12164-111">0x00008125</span><span class="sxs-lookup"><span data-stu-id="12164-111">0x00008125</span></span>  <br/> |
|<span data-ttu-id="12164-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12164-112">Data type:</span></span>  <br/> |<span data-ttu-id="12164-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="12164-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="12164-114">区域：</span><span class="sxs-lookup"><span data-stu-id="12164-114">Area:</span></span>  <br/> |<span data-ttu-id="12164-115">任务</span><span class="sxs-lookup"><span data-stu-id="12164-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12164-116">备注</span><span class="sxs-lookup"><span data-stu-id="12164-116">Remarks</span></span>

<span data-ttu-id="12164-117">发送任务请求之前，客户端将此属性设置为任务分配者的名称。</span><span class="sxs-lookup"><span data-stu-id="12164-117">Before sending a task request, the client sets this property to the name of the task assigner.</span></span> <span data-ttu-id="12164-118">发送任务响应之前，客户端将此属性设置为任务被分派人的名称。</span><span class="sxs-lookup"><span data-stu-id="12164-118">Before sending a task response, the client sets this property to the name of the task assignee.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="12164-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="12164-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12164-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="12164-120">Protocol specifications</span></span>

<span data-ttu-id="12164-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12164-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12164-122">提供属性集定义和对相关协议Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="12164-122">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12164-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12164-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12164-124">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="12164-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12164-125">头文件</span><span class="sxs-lookup"><span data-stu-id="12164-125">Header files</span></span>

<span data-ttu-id="12164-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12164-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="12164-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12164-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12164-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12164-128">See also</span></span>



[<span data-ttu-id="12164-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12164-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12164-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12164-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12164-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12164-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12164-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12164-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

