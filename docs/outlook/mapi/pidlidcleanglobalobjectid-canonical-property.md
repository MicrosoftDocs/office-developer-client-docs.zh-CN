---
title: PidLidCleanGlobalObjectId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCleanGlobalObjectId
api_type:
- COM
ms.assetid: 59b85997-7972-492e-9786-3f0f367dc3e3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 38442b763ec97969f73b11b346d638d547302715
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588998"
---
# <a name="pidlidcleanglobalobjectid-canonical-property"></a><span data-ttu-id="87251-103">PidLidCleanGlobalObjectId 规范属性</span><span class="sxs-lookup"><span data-stu-id="87251-103">PidLidCleanGlobalObjectId Canonical Property</span></span>

  
  
<span data-ttu-id="87251-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="87251-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="87251-105">指定清理全局**ObjectID**。</span><span class="sxs-lookup"><span data-stu-id="87251-105">Specifies the clean global **ObjectID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="87251-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="87251-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="87251-107">dispidCleanGlobalObjId</span><span class="sxs-lookup"><span data-stu-id="87251-107">dispidCleanGlobalObjId</span></span>  <br/> |
|<span data-ttu-id="87251-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="87251-108">Property set:</span></span>  <br/> |<span data-ttu-id="87251-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="87251-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="87251-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="87251-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="87251-111">0x00000023</span><span class="sxs-lookup"><span data-stu-id="87251-111">0x00000023</span></span>  <br/> |
|<span data-ttu-id="87251-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="87251-112">Data type:</span></span>  <br/> |<span data-ttu-id="87251-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="87251-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="87251-114">区域：</span><span class="sxs-lookup"><span data-stu-id="87251-114">Area:</span></span>  <br/> |<span data-ttu-id="87251-115">会议</span><span class="sxs-lookup"><span data-stu-id="87251-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="87251-116">注解</span><span class="sxs-lookup"><span data-stu-id="87251-116">Remarks</span></span>

<span data-ttu-id="87251-117">此属性的格式为**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 的相同。</span><span class="sxs-lookup"><span data-stu-id="87251-117">The format of this property is the same as that of **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)).</span></span> <span data-ttu-id="87251-118">此属性的值必须等于的**LID_GLOBAL_OBJID**，除 YH YL、 M、 值和 D 字段必须为零。</span><span class="sxs-lookup"><span data-stu-id="87251-118">The value of this property must be equal to the value of **LID_GLOBAL_OBJID**, except the YH, YL, M, and D fields must be zero.</span></span> <span data-ttu-id="87251-119">引用的定期系列 （包括孤立实例），以及定期系列本身，实例的所有对象都将都具有相同的该属性值。</span><span class="sxs-lookup"><span data-stu-id="87251-119">All objects that refer to an Instance of a recurring series (including an orphan instance), as well as the recurring series itself, will have the same value for this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="87251-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="87251-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="87251-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="87251-121">Protocol specifications</span></span>

<span data-ttu-id="87251-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87251-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87251-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="87251-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="87251-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87251-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87251-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="87251-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="87251-126">头文件</span><span class="sxs-lookup"><span data-stu-id="87251-126">Header files</span></span>

<span data-ttu-id="87251-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="87251-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="87251-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="87251-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87251-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87251-129">See also</span></span>



[<span data-ttu-id="87251-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87251-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="87251-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="87251-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="87251-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="87251-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="87251-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87251-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

