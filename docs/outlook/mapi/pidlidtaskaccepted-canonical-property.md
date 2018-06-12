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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7448768a0a35cbf53b481eab0571b405fead1544
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777065"
---
# <a name="pidlidtaskaccepted-canonical-property"></a><span data-ttu-id="30bd4-103">PidLidTaskAccepted 规范属性</span><span class="sxs-lookup"><span data-stu-id="30bd4-103">PidLidTaskAccepted Canonical Property</span></span>

  
  
<span data-ttu-id="30bd4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="30bd4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="30bd4-105">指示任务受托人已答复任务要求。</span><span class="sxs-lookup"><span data-stu-id="30bd4-105">Indicates whether a task assignee has replied to a task request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="30bd4-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="30bd4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="30bd4-107">dispidTaskAccepted</span><span class="sxs-lookup"><span data-stu-id="30bd4-107">dispidTaskAccepted</span></span>  <br/> |
|<span data-ttu-id="30bd4-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="30bd4-108">Property set:</span></span>  <br/> |<span data-ttu-id="30bd4-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="30bd4-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="30bd4-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="30bd4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="30bd4-111">0x00008108</span><span class="sxs-lookup"><span data-stu-id="30bd4-111">0x00008108</span></span>  <br/> |
|<span data-ttu-id="30bd4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="30bd4-112">Data type:</span></span>  <br/> |<span data-ttu-id="30bd4-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="30bd4-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="30bd4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="30bd4-114">Area:</span></span>  <br/> |<span data-ttu-id="30bd4-115">任务</span><span class="sxs-lookup"><span data-stu-id="30bd4-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="30bd4-116">备注</span><span class="sxs-lookup"><span data-stu-id="30bd4-116">Remarks</span></span>

<span data-ttu-id="30bd4-117">客户端将此属性设置为 FALSE 的新任务，或客户端将此属性设置为 TRUE 时接受或拒绝任务。</span><span class="sxs-lookup"><span data-stu-id="30bd4-117">The client sets this property to FALSE for a new task, or the client sets this property to TRUE when a task is either accepted or rejected.</span></span> <span data-ttu-id="30bd4-118">如果该属性不设置，则假定值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="30bd4-118">If the property is left unset, a value of FALSE is assumed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="30bd4-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="30bd4-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="30bd4-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="30bd4-120">Protocol specifications</span></span>

<span data-ttu-id="30bd4-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30bd4-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30bd4-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="30bd4-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="30bd4-123">[[MS OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="30bd4-123">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="30bd4-124">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="30bd4-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="30bd4-125">头文件</span><span class="sxs-lookup"><span data-stu-id="30bd4-125">Header files</span></span>

<span data-ttu-id="30bd4-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="30bd4-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="30bd4-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="30bd4-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="30bd4-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30bd4-128">See also</span></span>



[<span data-ttu-id="30bd4-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="30bd4-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="30bd4-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="30bd4-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="30bd4-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="30bd4-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="30bd4-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="30bd4-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

