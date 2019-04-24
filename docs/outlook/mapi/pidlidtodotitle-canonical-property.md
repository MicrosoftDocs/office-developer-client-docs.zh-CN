---
title: PidLidToDoTitle 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoTitle
api_type:
- COM
ms.assetid: 94cf031f-4c78-441d-9c01-55905b4974e0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7ed69d9bab84a5c572026bb9480249c1212e3376
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339940"
---
# <a name="pidlidtodotitle-canonical-property"></a><span data-ttu-id="79c74-103">PidLidToDoTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="79c74-103">PidLidToDoTitle Canonical Property</span></span>

  
  
<span data-ttu-id="79c74-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79c74-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79c74-105">包含用户 specifiable 文本, 用于在合并的待办工作列表中标识此 message 对象。</span><span class="sxs-lookup"><span data-stu-id="79c74-105">Contains user-specifiable text to identify this message object in a consolidated to-do list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="79c74-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="79c74-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="79c74-107">dispidToDoTitle</span><span class="sxs-lookup"><span data-stu-id="79c74-107">dispidToDoTitle</span></span>  <br/> |
|<span data-ttu-id="79c74-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="79c74-108">Property set:</span></span>  <br/> |<span data-ttu-id="79c74-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="79c74-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="79c74-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="79c74-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="79c74-111">0x000085A4</span><span class="sxs-lookup"><span data-stu-id="79c74-111">0x000085A4</span></span>  <br/> |
|<span data-ttu-id="79c74-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="79c74-112">Data type:</span></span>  <br/> |<span data-ttu-id="79c74-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="79c74-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="79c74-114">区域：</span><span class="sxs-lookup"><span data-stu-id="79c74-114">Area:</span></span>  <br/> |<span data-ttu-id="79c74-115">任务</span><span class="sxs-lookup"><span data-stu-id="79c74-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="79c74-116">注解</span><span class="sxs-lookup"><span data-stu-id="79c74-116">Remarks</span></span>

<span data-ttu-id="79c74-117">不得对任务设置此属性。</span><span class="sxs-lookup"><span data-stu-id="79c74-117">This property must not be set on a task.</span></span> <span data-ttu-id="79c74-118">若要指示一个空属性, 请不要将此属性设置为零长度字符串, 而是将其删除。</span><span class="sxs-lookup"><span data-stu-id="79c74-118">To indicate an empty property, do not set this property to the zero-length string, but instead delete it.</span></span> 
  
<span data-ttu-id="79c74-119">标记邮件对象时, 如果该属性不存在, 客户端应将**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 的值写入该属性。</span><span class="sxs-lookup"><span data-stu-id="79c74-119">When flagging a message object, and the property does not exist, a client should write the value of **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) to this property.</span></span>
  
<span data-ttu-id="79c74-120">在合并的待办任务列表中, 如果该属性不存在, 客户端应在待办任务列表中显示此属性时替换**PR_NORMALIZED_SUBJECT**属性的值。</span><span class="sxs-lookup"><span data-stu-id="79c74-120">In a consolidated to-do list, if this property does not exist, a client should substitute the value of the **PR_NORMALIZED_SUBJECT** property when displaying this property in the to-do list.</span></span> 
  
<span data-ttu-id="79c74-121">在草稿邮件对象上, 如果客户端实现发件人标志, 则应将此属性设置为与**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 相同的值。</span><span class="sxs-lookup"><span data-stu-id="79c74-121">On a draft message object, if the client implements sender flags, this property should be set to the same value as **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="79c74-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="79c74-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="79c74-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="79c74-123">Protocol specifications</span></span>

<span data-ttu-id="79c74-124">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="79c74-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="79c74-125">提供属性集定义和对相关 Exchange Server 协议规范的引用</span><span class="sxs-lookup"><span data-stu-id="79c74-125">Provides property set definitions and references to related Exchange Server protocol specifications</span></span>
    
<span data-ttu-id="79c74-126">[[毫秒-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="79c74-126">[[MS-OXOFLAG]](https://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="79c74-127">指定与标记相关的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="79c74-127">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="79c74-128">头文件</span><span class="sxs-lookup"><span data-stu-id="79c74-128">Header files</span></span>

<span data-ttu-id="79c74-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="79c74-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="79c74-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="79c74-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="79c74-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79c74-131">See also</span></span>



[<span data-ttu-id="79c74-132">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="79c74-132">PidTagNormalizedSubject Canonical Property</span></span>](pidtagnormalizedsubject-canonical-property.md)
  
[<span data-ttu-id="79c74-133">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="79c74-133">PidLidFlagRequest Canonical Property</span></span>](pidlidflagrequest-canonical-property.md)


[<span data-ttu-id="79c74-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="79c74-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="79c74-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="79c74-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="79c74-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="79c74-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="79c74-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="79c74-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

