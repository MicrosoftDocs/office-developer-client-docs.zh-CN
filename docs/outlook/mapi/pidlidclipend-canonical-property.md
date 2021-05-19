---
title: PidLidClipEnd 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidClipEnd
api_type:
- COM
ms.assetid: 17c8db96-80dd-4a7a-9a1b-ab1b37ba616c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 71a0a50f26b26d65ed34f38c2a0c7f930e6082a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349180"
---
# <a name="pidlidclipend-canonical-property"></a><span data-ttu-id="24e03-103">PidLidClipEnd 规范属性</span><span class="sxs-lookup"><span data-stu-id="24e03-103">PidLidClipEnd Canonical Property</span></span>

  
  
<span data-ttu-id="24e03-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24e03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24e03-105">为单个实例日历对象指定事件的结束日期和时间（以协调世界时 (UTC) 表示）。</span><span class="sxs-lookup"><span data-stu-id="24e03-105">Specifies the end date and time of the event in Coordinated Universal Time (UTC) for single instance calendar objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="24e03-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24e03-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24e03-107">dispidClipEnd</span><span class="sxs-lookup"><span data-stu-id="24e03-107">dispidClipEnd</span></span>  <br/> |
|<span data-ttu-id="24e03-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="24e03-108">Property set:</span></span>  <br/> |<span data-ttu-id="24e03-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="24e03-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="24e03-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="24e03-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="24e03-111">0x00008236</span><span class="sxs-lookup"><span data-stu-id="24e03-111">0x00008236</span></span>  <br/> |
|<span data-ttu-id="24e03-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24e03-112">Data type:</span></span>  <br/> |<span data-ttu-id="24e03-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="24e03-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="24e03-114">区域：</span><span class="sxs-lookup"><span data-stu-id="24e03-114">Area:</span></span>  <br/> |<span data-ttu-id="24e03-115">日历</span><span class="sxs-lookup"><span data-stu-id="24e03-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24e03-116">备注</span><span class="sxs-lookup"><span data-stu-id="24e03-116">Remarks</span></span>

<span data-ttu-id="24e03-117">对于单个实例日历对象，它以 UTC 格式指定事件的结束日期和时间。</span><span class="sxs-lookup"><span data-stu-id="24e03-117">For single instance calendar objects, it specifies the end date and time of the event in UTC.</span></span> <span data-ttu-id="24e03-118">对于定期系列，此属性以 UTC 格式指定最后一个定期系列实例的日期午夜，除非定期系列没有结束，在这种情况下，该值必须为 8 月 4500 年 8 月 31 日下午 11：59。</span><span class="sxs-lookup"><span data-stu-id="24e03-118">For a recurring series, this property specifies midnight on the date of the last instance of the recurring series in UTC, unless the recurring series has no end, in which case the value must be 31 August 4500, 11:59 p.m.</span></span>
  
<span data-ttu-id="24e03-119">此属性的值必须设置为 **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="24e03-119">The value of this property must be set to the value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="24e03-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="24e03-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24e03-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="24e03-121">Protocol specifications</span></span>

<span data-ttu-id="24e03-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24e03-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24e03-123">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="24e03-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="24e03-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24e03-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24e03-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="24e03-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24e03-126">头文件</span><span class="sxs-lookup"><span data-stu-id="24e03-126">Header files</span></span>

<span data-ttu-id="24e03-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="24e03-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="24e03-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24e03-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24e03-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24e03-129">See also</span></span>



[<span data-ttu-id="24e03-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24e03-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24e03-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24e03-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24e03-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24e03-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24e03-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24e03-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

