---
title: PidLidTaskLastUser 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastUser
api_type:
- COM
ms.assetid: 914c55e9-cb36-46a4-b5ee-382413fa25f9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 76311a76001b122bdfd984b9dedc37c2ff878fc7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360443"
---
# <a name="pidlidtasklastuser-canonical-property"></a><span data-ttu-id="4773a-103">PidLidTaskLastUser 规范属性</span><span class="sxs-lookup"><span data-stu-id="4773a-103">PidLidTaskLastUser Canonical Property</span></span>

  
  
<span data-ttu-id="4773a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4773a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4773a-105">命名作为任务所有者的最新用户。</span><span class="sxs-lookup"><span data-stu-id="4773a-105">Names the most recent user who was the task owner.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4773a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4773a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4773a-107">dispidTaskLastUser</span><span class="sxs-lookup"><span data-stu-id="4773a-107">dispidTaskLastUser</span></span>  <br/> |
|<span data-ttu-id="4773a-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="4773a-108">Property set:</span></span>  <br/> |<span data-ttu-id="4773a-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="4773a-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="4773a-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="4773a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4773a-111">0x00008122</span><span class="sxs-lookup"><span data-stu-id="4773a-111">0x00008122</span></span>  <br/> |
|<span data-ttu-id="4773a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4773a-112">Data type:</span></span>  <br/> |<span data-ttu-id="4773a-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4773a-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4773a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4773a-114">Area:</span></span>  <br/> |<span data-ttu-id="4773a-115">任务</span><span class="sxs-lookup"><span data-stu-id="4773a-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4773a-116">备注</span><span class="sxs-lookup"><span data-stu-id="4773a-116">Remarks</span></span>

<span data-ttu-id="4773a-117">在客户端发送任务请求之前，它会将此属性设置为任务分配者的名称。</span><span class="sxs-lookup"><span data-stu-id="4773a-117">Before a client sends a task request, it sets this property to the name of the task assigner.</span></span> <span data-ttu-id="4773a-118">在客户端发送任务接受之前，它会将此属性设置为任务受理人的名称。</span><span class="sxs-lookup"><span data-stu-id="4773a-118">Before a client sends a task acceptance, it sets this property to the name of the task assignee.</span></span> <span data-ttu-id="4773a-119">在客户端发送任务拒绝之前，它会将此属性设置为任务分配者的名称。</span><span class="sxs-lookup"><span data-stu-id="4773a-119">Before a client sends a task rejection, it sets this property to the name of the task assigner.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4773a-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="4773a-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4773a-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="4773a-121">Protocol specifications</span></span>

<span data-ttu-id="4773a-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4773a-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4773a-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="4773a-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4773a-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4773a-124">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4773a-125">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="4773a-125">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4773a-126">头文件</span><span class="sxs-lookup"><span data-stu-id="4773a-126">Header files</span></span>

<span data-ttu-id="4773a-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4773a-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="4773a-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4773a-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4773a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4773a-129">See also</span></span>



[<span data-ttu-id="4773a-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4773a-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4773a-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4773a-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4773a-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4773a-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4773a-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4773a-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

