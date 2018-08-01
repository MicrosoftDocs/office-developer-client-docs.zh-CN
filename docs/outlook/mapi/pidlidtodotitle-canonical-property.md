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
ms.openlocfilehash: 66208b2d31ca379389f3249abf281dd4d040e276
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777125"
---
# <a name="pidlidtodotitle-canonical-property"></a><span data-ttu-id="5a58d-103">PidLidToDoTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a58d-103">PidLidToDoTitle Canonical Property</span></span>

  
  
<span data-ttu-id="5a58d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5a58d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5a58d-105">包含要合并的待办事项列表中的此消息对象标识的用户并以此来文本。</span><span class="sxs-lookup"><span data-stu-id="5a58d-105">Contains user-specifiable text to identify this message object in a consolidated to-do list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5a58d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5a58d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5a58d-107">dispidToDoTitle</span><span class="sxs-lookup"><span data-stu-id="5a58d-107">dispidToDoTitle</span></span>  <br/> |
|<span data-ttu-id="5a58d-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="5a58d-108">Property set:</span></span>  <br/> |<span data-ttu-id="5a58d-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5a58d-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5a58d-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="5a58d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="5a58d-111">0x000085A4</span><span class="sxs-lookup"><span data-stu-id="5a58d-111">0x000085A4</span></span>  <br/> |
|<span data-ttu-id="5a58d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5a58d-112">Data type:</span></span>  <br/> |<span data-ttu-id="5a58d-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5a58d-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5a58d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5a58d-114">Area:</span></span>  <br/> |<span data-ttu-id="5a58d-115">Task</span><span class="sxs-lookup"><span data-stu-id="5a58d-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5a58d-116">说明</span><span class="sxs-lookup"><span data-stu-id="5a58d-116">Remarks</span></span>

<span data-ttu-id="5a58d-117">此属性必须设置对任务。</span><span class="sxs-lookup"><span data-stu-id="5a58d-117">This property must not be set on a task.</span></span> <span data-ttu-id="5a58d-118">若要指示属性为空，未将此属性设置为零长度字符串中，但而是将其删除。</span><span class="sxs-lookup"><span data-stu-id="5a58d-118">To indicate an empty property, do not set this property to the zero-length string, but instead delete it.</span></span> 
  
<span data-ttu-id="5a58d-119">标记邮件对象和属性不存在，当客户端应**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) 的值都写入到此属性。</span><span class="sxs-lookup"><span data-stu-id="5a58d-119">When flagging a message object, and the property does not exist, a client should write the value of **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) to this property.</span></span>
  
<span data-ttu-id="5a58d-120">在合并待办事项列表中，如果此属性不存在，则客户端应在待办事项列表中显示此属性时替换**PR_NORMALIZED_SUBJECT**属性的值。</span><span class="sxs-lookup"><span data-stu-id="5a58d-120">In a consolidated to-do list, if this property does not exist, a client should substitute the value of the **PR_NORMALIZED_SUBJECT** property when displaying this property in the to-do list.</span></span> 
  
<span data-ttu-id="5a58d-121">在草稿 message 对象，如果客户端实现发件人标志，此属性应设置为**dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) 相同的值。</span><span class="sxs-lookup"><span data-stu-id="5a58d-121">On a draft message object, if the client implements sender flags, this property should be set to the same value as **dispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5a58d-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="5a58d-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5a58d-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="5a58d-123">Protocol specifications</span></span>

<span data-ttu-id="5a58d-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a58d-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a58d-125">提供属性集定义和相关的 Exchange Server 协议规范的引用</span><span class="sxs-lookup"><span data-stu-id="5a58d-125">Provides property set definitions and references to related Exchange Server protocol specifications</span></span>
    
<span data-ttu-id="5a58d-126">[[MS OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5a58d-126">[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5a58d-127">指定的属性和与标记的操作。</span><span class="sxs-lookup"><span data-stu-id="5a58d-127">Specifies the properties and operations related to flagging.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5a58d-128">头文件</span><span class="sxs-lookup"><span data-stu-id="5a58d-128">Header files</span></span>

<span data-ttu-id="5a58d-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5a58d-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="5a58d-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5a58d-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5a58d-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a58d-131">See also</span></span>



[<span data-ttu-id="5a58d-132">PidTagNormalizedSubject 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a58d-132">PidTagNormalizedSubject Canonical Property</span></span>](pidtagnormalizedsubject-canonical-property.md)
  
[<span data-ttu-id="5a58d-133">PidLidFlagRequest 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a58d-133">PidLidFlagRequest Canonical Property</span></span>](pidlidflagrequest-canonical-property.md)


[<span data-ttu-id="5a58d-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5a58d-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5a58d-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5a58d-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5a58d-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5a58d-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5a58d-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5a58d-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

