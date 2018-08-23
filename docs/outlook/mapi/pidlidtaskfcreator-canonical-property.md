---
title: PidLidTaskFCreator 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskFCreator
api_type:
- COM
ms.assetid: bb88750b-4773-4241-aa38-462a2634dbcb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9cbd237e80f4862683c1fa914f8261f8351b148e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589019"
---
# <a name="pidlidtaskfcreator-canonical-property"></a><span data-ttu-id="dfd5a-103">PidLidTaskFCreator 规范属性</span><span class="sxs-lookup"><span data-stu-id="dfd5a-103">PidLidTaskFCreator Canonical Property</span></span>

  
  
<span data-ttu-id="dfd5a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dfd5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dfd5a-105">指示任务最初创建由当前用户或用户代理，而不是通过处理任务要求。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-105">Indicates the task was originally created by the current user or user agent instead of by processing a task request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dfd5a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dfd5a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dfd5a-107">dispidTaskFCreator</span><span class="sxs-lookup"><span data-stu-id="dfd5a-107">dispidTaskFCreator</span></span>  <br/> |
|<span data-ttu-id="dfd5a-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="dfd5a-108">Property set:</span></span>  <br/> |<span data-ttu-id="dfd5a-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="dfd5a-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="dfd5a-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="dfd5a-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dfd5a-111">0x0000811E</span><span class="sxs-lookup"><span data-stu-id="dfd5a-111">0x0000811E</span></span>  <br/> |
|<span data-ttu-id="dfd5a-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dfd5a-112">Data type:</span></span>  <br/> |<span data-ttu-id="dfd5a-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="dfd5a-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="dfd5a-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dfd5a-114">Area:</span></span>  <br/> |<span data-ttu-id="dfd5a-115">Task</span><span class="sxs-lookup"><span data-stu-id="dfd5a-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dfd5a-116">注解</span><span class="sxs-lookup"><span data-stu-id="dfd5a-116">Remarks</span></span>

<span data-ttu-id="dfd5a-117">客户端设置此属性为 TRUE 时用户创建任务和为 FALSE 时由另一个用户分配任务。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-117">The client sets this property to TRUE when the user creates the task and to FALSE when the task is assigned by another user.</span></span> <span data-ttu-id="dfd5a-118">如果不设置此属性，则假定值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-118">If this property is left unset, a value of TRUE is assumed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dfd5a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="dfd5a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dfd5a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="dfd5a-120">Protocol specifications</span></span>

<span data-ttu-id="dfd5a-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dfd5a-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dfd5a-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dfd5a-123">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dfd5a-123">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dfd5a-124">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dfd5a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="dfd5a-125">Header files</span></span>

<span data-ttu-id="dfd5a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dfd5a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="dfd5a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dfd5a-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dfd5a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd5a-128">See also</span></span>



[<span data-ttu-id="dfd5a-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dfd5a-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dfd5a-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dfd5a-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dfd5a-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dfd5a-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dfd5a-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dfd5a-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

