---
title: PidLidAllAttendeesString 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAllAttendeesString
api_type:
- COM
ms.assetid: 2ffc0609-341d-4e35-8f53-ed3096c6fa7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96ad0727797475effd0563e4753070cb3bac4b37
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334774"
---
# <a name="pidlidallattendeesstring-canonical-property"></a><span data-ttu-id="1bfe4-103">PidLidAllAttendeesString 规范属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-103">PidLidAllAttendeesString Canonical Property</span></span>

  
  
<span data-ttu-id="1bfe4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1bfe4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1bfe4-105">指定除组织者之外的所有与会者的列表, 包括资源和 unsendable 与会者。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-105">Specifies a list of all the attendees except for the organizer, including resources and unsendable attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1bfe4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1bfe4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1bfe4-107">dispidAllAttendeesString</span><span class="sxs-lookup"><span data-stu-id="1bfe4-107">dispidAllAttendeesString</span></span>  <br/> |
|<span data-ttu-id="1bfe4-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="1bfe4-108">Property set:</span></span>  <br/> |<span data-ttu-id="1bfe4-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="1bfe4-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="1bfe4-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="1bfe4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="1bfe4-111">0x00008238</span><span class="sxs-lookup"><span data-stu-id="1bfe4-111">0x00008238</span></span>  <br/> |
|<span data-ttu-id="1bfe4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1bfe4-112">Data type:</span></span>  <br/> |<span data-ttu-id="1bfe4-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1bfe4-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1bfe4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="1bfe4-114">Area:</span></span>  <br/> |<span data-ttu-id="1bfe4-115">会议</span><span class="sxs-lookup"><span data-stu-id="1bfe4-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1bfe4-116">注解</span><span class="sxs-lookup"><span data-stu-id="1bfe4-116">Remarks</span></span>

<span data-ttu-id="1bfe4-117">每个与会者的值都是与会者的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-117">The value for each attendee is the attendee's display name.</span></span> <span data-ttu-id="1bfe4-118">单独的条目必须用分号分隔, 后跟空格。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="1bfe4-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1bfe4-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="1bfe4-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1bfe4-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="1bfe4-121">Protocol specifications</span></span>

<span data-ttu-id="1bfe4-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1bfe4-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1bfe4-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1bfe4-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1bfe4-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1bfe4-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1bfe4-126">头文件</span><span class="sxs-lookup"><span data-stu-id="1bfe4-126">Header files</span></span>

<span data-ttu-id="1bfe4-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1bfe4-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="1bfe4-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1bfe4-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1bfe4-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bfe4-129">See also</span></span>



[<span data-ttu-id="1bfe4-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1bfe4-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1bfe4-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1bfe4-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1bfe4-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1bfe4-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1bfe4-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

