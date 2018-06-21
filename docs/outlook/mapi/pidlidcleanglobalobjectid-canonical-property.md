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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: a784c91a04cce572c8e30085b1760c28296a1d53
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19776730"
---
# <a name="pidlidcleanglobalobjectid-canonical-property"></a><span data-ttu-id="6cdd0-103">PidLidCleanGlobalObjectId 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cdd0-103">PidLidCleanGlobalObjectId Canonical Property</span></span>

  
  
<span data-ttu-id="6cdd0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6cdd0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6cdd0-105">指定清理全局**ObjectID**。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-105">Specifies the clean global **ObjectID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6cdd0-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6cdd0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6cdd0-107">dispidCleanGlobalObjId</span><span class="sxs-lookup"><span data-stu-id="6cdd0-107">dispidCleanGlobalObjId</span></span>  <br/> |
|<span data-ttu-id="6cdd0-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6cdd0-108">Property set:</span></span>  <br/> |<span data-ttu-id="6cdd0-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="6cdd0-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="6cdd0-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6cdd0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6cdd0-111">0x00000023</span><span class="sxs-lookup"><span data-stu-id="6cdd0-111">0x00000023</span></span>  <br/> |
|<span data-ttu-id="6cdd0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6cdd0-112">Data type:</span></span>  <br/> |<span data-ttu-id="6cdd0-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6cdd0-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6cdd0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6cdd0-114">Area:</span></span>  <br/> |<span data-ttu-id="6cdd0-115">会议</span><span class="sxs-lookup"><span data-stu-id="6cdd0-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6cdd0-116">注解</span><span class="sxs-lookup"><span data-stu-id="6cdd0-116">Remarks</span></span>

<span data-ttu-id="6cdd0-117">此属性的格式为**LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)) 的相同。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-117">The format of this property is the same as that of **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)).</span></span> <span data-ttu-id="6cdd0-118">此属性的值必须等于的**LID_GLOBAL_OBJID**，除 YH YL、 M、 值和 D 字段必须为零。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-118">The value of this property must be equal to the value of **LID_GLOBAL_OBJID**, except the YH, YL, M, and D fields must be zero.</span></span> <span data-ttu-id="6cdd0-119">引用的定期系列 （包括孤立实例），以及定期系列本身，实例的所有对象都将都具有相同的该属性值。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-119">All objects that refer to an Instance of a recurring series (including an orphan instance), as well as the recurring series itself, will have the same value for this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6cdd0-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="6cdd0-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6cdd0-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="6cdd0-121">Protocol specifications</span></span>

<span data-ttu-id="6cdd0-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cdd0-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cdd0-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6cdd0-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6cdd0-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6cdd0-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6cdd0-126">头文件</span><span class="sxs-lookup"><span data-stu-id="6cdd0-126">Header files</span></span>

<span data-ttu-id="6cdd0-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6cdd0-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="6cdd0-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6cdd0-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6cdd0-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cdd0-129">See also</span></span>



[<span data-ttu-id="6cdd0-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6cdd0-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6cdd0-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6cdd0-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6cdd0-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6cdd0-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6cdd0-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6cdd0-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

