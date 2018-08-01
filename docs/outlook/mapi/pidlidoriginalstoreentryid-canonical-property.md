---
title: PidLidOriginalStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOriginalStoreEntryId
api_type:
- COM
ms.assetid: 1b1fc008-9cd5-49f6-9f91-b59e305a1e82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aaf442b941cfe14f695bf5e7f7ec246d06e5ae0b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776937"
---
# <a name="pidlidoriginalstoreentryid-canonical-property"></a><span data-ttu-id="74b46-103">PidLidOriginalStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="74b46-103">PidLidOriginalStoreEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="74b46-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="74b46-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="74b46-105">指定 delegator 存储的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="74b46-105">Specifies the entry ID of the delegator's store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="74b46-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="74b46-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="74b46-107">dispidOrigStoreEid</span><span class="sxs-lookup"><span data-stu-id="74b46-107">dispidOrigStoreEid</span></span>  <br/> |
|<span data-ttu-id="74b46-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="74b46-108">Property set:</span></span>  <br/> |<span data-ttu-id="74b46-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="74b46-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="74b46-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="74b46-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="74b46-111">0x00008237</span><span class="sxs-lookup"><span data-stu-id="74b46-111">0x00008237</span></span>  <br/> |
|<span data-ttu-id="74b46-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="74b46-112">Data type:</span></span>  <br/> |<span data-ttu-id="74b46-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="74b46-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="74b46-114">区域：</span><span class="sxs-lookup"><span data-stu-id="74b46-114">Area:</span></span>  <br/> |<span data-ttu-id="74b46-115">会议</span><span class="sxs-lookup"><span data-stu-id="74b46-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="74b46-116">说明</span><span class="sxs-lookup"><span data-stu-id="74b46-116">Remarks</span></span>

<span data-ttu-id="74b46-117">此属性应在会议对象的已创建或更新由代理设置。</span><span class="sxs-lookup"><span data-stu-id="74b46-117">This property should be set on meeting objects which have been created or updated by a delegate.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="74b46-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="74b46-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="74b46-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="74b46-119">Protocol specifications</span></span>

<span data-ttu-id="74b46-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="74b46-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="74b46-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="74b46-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="74b46-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="74b46-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="74b46-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="74b46-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="74b46-124">头文件</span><span class="sxs-lookup"><span data-stu-id="74b46-124">Header files</span></span>

<span data-ttu-id="74b46-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="74b46-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="74b46-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="74b46-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74b46-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74b46-127">See also</span></span>



[<span data-ttu-id="74b46-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="74b46-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="74b46-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="74b46-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="74b46-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="74b46-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="74b46-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="74b46-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

