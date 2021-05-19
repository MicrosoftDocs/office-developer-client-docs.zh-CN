---
title: PidLidAppointmentProposedEndWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentProposedEndWhole
api_type:
- COM
ms.assetid: 6749e7b1-7a66-4aca-92b0-9a23a87fc121
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ae1ac42e9f293383a10b52d9f9a5bd655cd38ef4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346401"
---
# <a name="pidlidappointmentproposedendwhole-canonical-property"></a><span data-ttu-id="2e17f-103">PidLidAppointmentProposedEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e17f-103">PidLidAppointmentProposedEndWhole Canonical Property</span></span>

  
  
<span data-ttu-id="2e17f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e17f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e17f-105">指定计数器建议的 **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="2e17f-105">Specifies the proposed value for the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property for a counter proposal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e17f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e17f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e17f-107">dispidApptProposedEndWhole</span><span class="sxs-lookup"><span data-stu-id="2e17f-107">dispidApptProposedEndWhole</span></span>  <br/> |
|<span data-ttu-id="2e17f-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="2e17f-108">Property set:</span></span>  <br/> |<span data-ttu-id="2e17f-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="2e17f-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="2e17f-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="2e17f-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2e17f-111">0x00008251</span><span class="sxs-lookup"><span data-stu-id="2e17f-111">0x00008251</span></span>  <br/> |
|<span data-ttu-id="2e17f-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e17f-112">Data type:</span></span>  <br/> |<span data-ttu-id="2e17f-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2e17f-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="2e17f-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2e17f-114">Area:</span></span>  <br/> |<span data-ttu-id="2e17f-115">会议</span><span class="sxs-lookup"><span data-stu-id="2e17f-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e17f-116">备注</span><span class="sxs-lookup"><span data-stu-id="2e17f-116">Remarks</span></span>

<span data-ttu-id="2e17f-117">此值必须以协调世界时 utc (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="2e17f-117">This value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e17f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e17f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e17f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e17f-119">Protocol specifications</span></span>

<span data-ttu-id="2e17f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e17f-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e17f-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="2e17f-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2e17f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e17f-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e17f-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2e17f-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e17f-124">头文件</span><span class="sxs-lookup"><span data-stu-id="2e17f-124">Header files</span></span>

<span data-ttu-id="2e17f-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e17f-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e17f-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e17f-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e17f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e17f-127">See also</span></span>



[<span data-ttu-id="2e17f-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e17f-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e17f-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e17f-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e17f-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e17f-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e17f-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e17f-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

