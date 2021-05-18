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
ms.openlocfilehash: dfb49fafcc2dc368e84786b526869e0447ccaf8c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303078"
---
# <a name="pidlidtaskfcreator-canonical-property"></a><span data-ttu-id="12d42-103">PidLidTaskFCreator 规范属性</span><span class="sxs-lookup"><span data-stu-id="12d42-103">PidLidTaskFCreator Canonical Property</span></span>

  
  
<span data-ttu-id="12d42-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12d42-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12d42-105">指示任务最初是由当前用户或用户代理创建的，而不是通过处理任务请求创建的。</span><span class="sxs-lookup"><span data-stu-id="12d42-105">Indicates the task was originally created by the current user or user agent instead of by processing a task request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="12d42-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12d42-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="12d42-107">dispidTaskFCreator</span><span class="sxs-lookup"><span data-stu-id="12d42-107">dispidTaskFCreator</span></span>  <br/> |
|<span data-ttu-id="12d42-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="12d42-108">Property set:</span></span>  <br/> |<span data-ttu-id="12d42-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="12d42-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="12d42-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="12d42-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="12d42-111">0x0000811E</span><span class="sxs-lookup"><span data-stu-id="12d42-111">0x0000811E</span></span>  <br/> |
|<span data-ttu-id="12d42-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12d42-112">Data type:</span></span>  <br/> |<span data-ttu-id="12d42-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="12d42-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="12d42-114">区域：</span><span class="sxs-lookup"><span data-stu-id="12d42-114">Area:</span></span>  <br/> |<span data-ttu-id="12d42-115">任务</span><span class="sxs-lookup"><span data-stu-id="12d42-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12d42-116">备注</span><span class="sxs-lookup"><span data-stu-id="12d42-116">Remarks</span></span>

<span data-ttu-id="12d42-117">当用户创建任务时，客户端将此属性设置为 TRUE;如果任务由另一个用户分配，则此属性将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="12d42-117">The client sets this property to TRUE when the user creates the task and to FALSE when the task is assigned by another user.</span></span> <span data-ttu-id="12d42-118">如果该属性未设置，则假定值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="12d42-118">If this property is left unset, a value of TRUE is assumed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="12d42-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="12d42-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12d42-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="12d42-120">Protocol specifications</span></span>

<span data-ttu-id="12d42-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12d42-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12d42-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="12d42-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12d42-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12d42-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12d42-124">定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。</span><span class="sxs-lookup"><span data-stu-id="12d42-124">Defines several objects that model the electronic equivalent of tasks, task assignments, and task updates.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12d42-125">头文件</span><span class="sxs-lookup"><span data-stu-id="12d42-125">Header files</span></span>

<span data-ttu-id="12d42-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12d42-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="12d42-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12d42-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12d42-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12d42-128">See also</span></span>



[<span data-ttu-id="12d42-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12d42-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12d42-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12d42-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12d42-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12d42-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12d42-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12d42-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

