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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a31e2862aa3a6265f1dd9f8036abe329cf556276
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777114"
---
# <a name="pidlidtaskversion-canonical-property"></a><span data-ttu-id="32ebf-103">PidLidTaskVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="32ebf-103">PidLidTaskVersion Canonical Property</span></span>

  
  
<span data-ttu-id="32ebf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="32ebf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="32ebf-105">指示任务的最新更新的副本。</span><span class="sxs-lookup"><span data-stu-id="32ebf-105">Indicates which copy is the latest update of a task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="32ebf-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="32ebf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="32ebf-107">dispidTaskVersion</span><span class="sxs-lookup"><span data-stu-id="32ebf-107">dispidTaskVersion</span></span>  <br/> |
|<span data-ttu-id="32ebf-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="32ebf-108">Property set:</span></span>  <br/> |<span data-ttu-id="32ebf-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="32ebf-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="32ebf-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="32ebf-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="32ebf-111">0x00008112</span><span class="sxs-lookup"><span data-stu-id="32ebf-111">0x00008112</span></span>  <br/> |
|<span data-ttu-id="32ebf-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="32ebf-112">Data type:</span></span>  <br/> |<span data-ttu-id="32ebf-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="32ebf-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="32ebf-114">区域：</span><span class="sxs-lookup"><span data-stu-id="32ebf-114">Area:</span></span>  <br/> |<span data-ttu-id="32ebf-115">任务</span><span class="sxs-lookup"><span data-stu-id="32ebf-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="32ebf-116">备注</span><span class="sxs-lookup"><span data-stu-id="32ebf-116">Remarks</span></span>

<span data-ttu-id="32ebf-117">与比任务的更低版本的更新将被忽略。</span><span class="sxs-lookup"><span data-stu-id="32ebf-117">Updates with lower versions than the task are ignored.</span></span> 
  
<span data-ttu-id="32ebf-118">任务的通信中嵌入任务时, 客户端设置任务通信以及嵌入的任务的当前版本。</span><span class="sxs-lookup"><span data-stu-id="32ebf-118">When embedding a task in a task communication, the client sets the current version of the embedded task on the task communication as well.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="32ebf-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="32ebf-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="32ebf-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="32ebf-120">Protocol specifications</span></span>

<span data-ttu-id="32ebf-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32ebf-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32ebf-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="32ebf-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="32ebf-123">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="32ebf-123">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="32ebf-124">定义模型的任务、 任务分配和任务更新电子等效项的多个对象。</span><span class="sxs-lookup"><span data-stu-id="32ebf-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="32ebf-125">头文件</span><span class="sxs-lookup"><span data-stu-id="32ebf-125">Header files</span></span>

<span data-ttu-id="32ebf-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="32ebf-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="32ebf-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="32ebf-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="32ebf-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32ebf-128">See also</span></span>



[<span data-ttu-id="32ebf-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="32ebf-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="32ebf-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="32ebf-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="32ebf-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32ebf-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="32ebf-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="32ebf-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

