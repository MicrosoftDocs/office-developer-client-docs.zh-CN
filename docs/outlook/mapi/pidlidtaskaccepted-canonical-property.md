---
title: PidLidTaskAccepted 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAccepted
api_type:
- COM
ms.assetid: 8e31f893-b639-43da-a535-662153c82d82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0172bf0d69c3f345b592364be754f58c9e7a4420
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331281"
---
# <a name="pidlidtaskaccepted-canonical-property"></a><span data-ttu-id="82709-103">PidLidTaskAccepted 规范属性</span><span class="sxs-lookup"><span data-stu-id="82709-103">PidLidTaskAccepted Canonical Property</span></span>

  
  
<span data-ttu-id="82709-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82709-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82709-105">指示任务受理人是否已答复任务请求。</span><span class="sxs-lookup"><span data-stu-id="82709-105">Indicates whether a task assignee has replied to a task request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82709-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="82709-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="82709-107">dispidTaskAccepted</span><span class="sxs-lookup"><span data-stu-id="82709-107">dispidTaskAccepted</span></span>  <br/> |
|<span data-ttu-id="82709-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="82709-108">Property set:</span></span>  <br/> |<span data-ttu-id="82709-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="82709-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="82709-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="82709-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="82709-111">0x00008108</span><span class="sxs-lookup"><span data-stu-id="82709-111">0x00008108</span></span>  <br/> |
|<span data-ttu-id="82709-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="82709-112">Data type:</span></span>  <br/> |<span data-ttu-id="82709-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="82709-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="82709-114">区域：</span><span class="sxs-lookup"><span data-stu-id="82709-114">Area:</span></span>  <br/> |<span data-ttu-id="82709-115">任务</span><span class="sxs-lookup"><span data-stu-id="82709-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="82709-116">注解</span><span class="sxs-lookup"><span data-stu-id="82709-116">Remarks</span></span>

<span data-ttu-id="82709-117">客户端将新任务的此属性设置为 FALSE, 或者客户端在任务被接受或拒绝时将此属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="82709-117">The client sets this property to FALSE for a new task, or the client sets this property to TRUE when a task is either accepted or rejected.</span></span> <span data-ttu-id="82709-118">如果未设置该属性, 则假定值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="82709-118">If the property is left unset, a value of FALSE is assumed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="82709-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="82709-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="82709-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="82709-120">Protocol specifications</span></span>

<span data-ttu-id="82709-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="82709-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="82709-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="82709-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="82709-123">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="82709-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="82709-124">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="82709-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="82709-125">头文件</span><span class="sxs-lookup"><span data-stu-id="82709-125">Header files</span></span>

<span data-ttu-id="82709-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="82709-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="82709-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="82709-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="82709-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82709-128">See also</span></span>



[<span data-ttu-id="82709-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="82709-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="82709-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="82709-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="82709-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="82709-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="82709-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="82709-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

