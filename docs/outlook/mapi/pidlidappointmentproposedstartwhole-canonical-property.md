---
title: PidLidAppointmentProposedStartWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentProposedStartWhole
api_type:
- COM
ms.assetid: acc96b0a-bffb-46ef-8c46-b831d165a346
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 064e57310223de2bcaaf084f7c79d2295fc5bf5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339303"
---
# <a name="pidlidappointmentproposedstartwhole-canonical-property"></a><span data-ttu-id="90873-103">PidLidAppointmentProposedStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="90873-103">PidLidAppointmentProposedStartWhole Canonical Property</span></span>

  
  
<span data-ttu-id="90873-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="90873-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="90873-105">为计数器建议指定 **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 建议的值。</span><span class="sxs-lookup"><span data-stu-id="90873-105">Specifies the proposed value for **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) for a counter proposal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="90873-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="90873-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="90873-107">dispidApptProposedStartWhole</span><span class="sxs-lookup"><span data-stu-id="90873-107">dispidApptProposedStartWhole</span></span>  <br/> |
|<span data-ttu-id="90873-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="90873-108">Property set:</span></span>  <br/> |<span data-ttu-id="90873-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="90873-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="90873-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="90873-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="90873-111">0x00008250</span><span class="sxs-lookup"><span data-stu-id="90873-111">0x00008250</span></span>  <br/> |
|<span data-ttu-id="90873-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="90873-112">Data type:</span></span>  <br/> |<span data-ttu-id="90873-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="90873-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="90873-114">区域：</span><span class="sxs-lookup"><span data-stu-id="90873-114">Area:</span></span>  <br/> |<span data-ttu-id="90873-115">会议</span><span class="sxs-lookup"><span data-stu-id="90873-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="90873-116">备注</span><span class="sxs-lookup"><span data-stu-id="90873-116">Remarks</span></span>

<span data-ttu-id="90873-117">此值必须以协调世界时 utc (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="90873-117">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="90873-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="90873-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="90873-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="90873-119">Protocol specifications</span></span>

<span data-ttu-id="90873-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90873-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90873-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="90873-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="90873-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="90873-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="90873-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="90873-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="90873-124">头文件</span><span class="sxs-lookup"><span data-stu-id="90873-124">Header files</span></span>

<span data-ttu-id="90873-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="90873-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="90873-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="90873-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="90873-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90873-127">See also</span></span>



[<span data-ttu-id="90873-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="90873-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="90873-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="90873-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="90873-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="90873-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="90873-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="90873-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

