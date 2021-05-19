---
title: PidLidTaskVersion 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskVersion
api_type:
- COM
ms.assetid: 3ab77f25-ad11-4501-8d35-ef560c07e2f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3daf8a04afc9cf47d808b46f2cee010e15a33cf9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356490"
---
# <a name="pidlidtaskversion-canonical-property"></a><span data-ttu-id="b61fa-103">PidLidTaskVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="b61fa-103">PidLidTaskVersion Canonical Property</span></span>

  
  
<span data-ttu-id="b61fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b61fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b61fa-105">指示哪个副本是任务的最新更新。</span><span class="sxs-lookup"><span data-stu-id="b61fa-105">Indicates which copy is the latest update of a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b61fa-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b61fa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b61fa-107">dispidTaskVersion</span><span class="sxs-lookup"><span data-stu-id="b61fa-107">dispidTaskVersion</span></span>  <br/> |
|<span data-ttu-id="b61fa-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="b61fa-108">Property set:</span></span>  <br/> |<span data-ttu-id="b61fa-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="b61fa-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="b61fa-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="b61fa-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b61fa-111">0x00008112</span><span class="sxs-lookup"><span data-stu-id="b61fa-111">0x00008112</span></span>  <br/> |
|<span data-ttu-id="b61fa-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b61fa-112">Data type:</span></span>  <br/> |<span data-ttu-id="b61fa-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b61fa-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b61fa-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b61fa-114">Area:</span></span>  <br/> |<span data-ttu-id="b61fa-115">任务</span><span class="sxs-lookup"><span data-stu-id="b61fa-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b61fa-116">备注</span><span class="sxs-lookup"><span data-stu-id="b61fa-116">Remarks</span></span>

<span data-ttu-id="b61fa-117">版本低于任务的更新将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b61fa-117">Updates with lower versions than the task are ignored.</span></span> 
  
<span data-ttu-id="b61fa-118">在任务通信中嵌入任务时，客户端还设置任务通信中嵌入任务的当前版本。</span><span class="sxs-lookup"><span data-stu-id="b61fa-118">When embedding a task in a task communication, the client sets the current version of the embedded task on the task communication as well.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b61fa-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b61fa-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b61fa-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b61fa-120">Protocol specifications</span></span>

<span data-ttu-id="b61fa-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b61fa-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b61fa-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="b61fa-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b61fa-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b61fa-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b61fa-124">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="b61fa-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b61fa-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b61fa-125">Header files</span></span>

<span data-ttu-id="b61fa-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b61fa-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b61fa-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b61fa-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b61fa-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b61fa-128">See also</span></span>



[<span data-ttu-id="b61fa-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b61fa-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b61fa-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b61fa-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b61fa-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b61fa-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b61fa-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b61fa-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

