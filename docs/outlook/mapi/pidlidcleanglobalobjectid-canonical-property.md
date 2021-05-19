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
ms.openlocfilehash: c48fa333d407492b69da5287fa75c565bfd10e11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349215"
---
# <a name="pidlidcleanglobalobjectid-canonical-property"></a><span data-ttu-id="81082-103">PidLidCleanGlobalObjectId 规范属性</span><span class="sxs-lookup"><span data-stu-id="81082-103">PidLidCleanGlobalObjectId Canonical Property</span></span>

  
  
<span data-ttu-id="81082-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81082-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81082-105">指定干净的全局 **ObjectID**。</span><span class="sxs-lookup"><span data-stu-id="81082-105">Specifies the clean global **ObjectID**.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="81082-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="81082-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="81082-107">dispidCleanGlobalObjId</span><span class="sxs-lookup"><span data-stu-id="81082-107">dispidCleanGlobalObjId</span></span>  <br/> |
|<span data-ttu-id="81082-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="81082-108">Property set:</span></span>  <br/> |<span data-ttu-id="81082-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="81082-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="81082-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="81082-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="81082-111">0x00000023</span><span class="sxs-lookup"><span data-stu-id="81082-111">0x00000023</span></span>  <br/> |
|<span data-ttu-id="81082-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="81082-112">Data type:</span></span>  <br/> |<span data-ttu-id="81082-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="81082-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="81082-114">区域：</span><span class="sxs-lookup"><span data-stu-id="81082-114">Area:</span></span>  <br/> |<span data-ttu-id="81082-115">会议</span><span class="sxs-lookup"><span data-stu-id="81082-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="81082-116">备注</span><span class="sxs-lookup"><span data-stu-id="81082-116">Remarks</span></span>

<span data-ttu-id="81082-117">此属性的格式与[PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md) LID_GLOBAL_OBJID (的格式) 。 </span><span class="sxs-lookup"><span data-stu-id="81082-117">The format of this property is the same as that of **LID_GLOBAL_OBJID** ([PidLidGlobalObjectId](pidlidglobalobjectid-canonical-property.md)).</span></span> <span data-ttu-id="81082-118">此属性的值必须等于 **LID_GLOBAL_OBJID，** 但 YH、YL、M 和 D 字段必须为零。</span><span class="sxs-lookup"><span data-stu-id="81082-118">The value of this property must be equal to the value of **LID_GLOBAL_OBJID**, except the YH, YL, M, and D fields must be zero.</span></span> <span data-ttu-id="81082-119">引用定期系列实例的所有对象 (包括孤立实例) 以及定期系列本身）的此属性具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="81082-119">All objects that refer to an Instance of a recurring series (including an orphan instance), as well as the recurring series itself, will have the same value for this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="81082-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="81082-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="81082-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="81082-121">Protocol specifications</span></span>

<span data-ttu-id="81082-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81082-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81082-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="81082-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="81082-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="81082-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="81082-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="81082-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="81082-126">头文件</span><span class="sxs-lookup"><span data-stu-id="81082-126">Header files</span></span>

<span data-ttu-id="81082-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="81082-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="81082-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="81082-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="81082-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81082-129">See also</span></span>



[<span data-ttu-id="81082-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="81082-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="81082-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="81082-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="81082-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="81082-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="81082-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="81082-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

