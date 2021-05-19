---
title: PidLidAttendeeCriticalChange 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAttendeeCriticalChange
api_type:
- COM
ms.assetid: 2b46966d-c63d-4241-92d4-001d6a674e97
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d6464a346d8543a128ec1af9f605667c6a51ca3c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342040"
---
# <a name="pidlidattendeecriticalchange-canonical-property"></a><span data-ttu-id="2e6a9-103">PidLidAttendeeCriticalChange 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e6a9-103">PidLidAttendeeCriticalChange Canonical Property</span></span>

  
  
<span data-ttu-id="2e6a9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e6a9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e6a9-105">指定发送与会议相关的对象的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2e6a9-105">Specifies the date and time when the meeting-related object was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e6a9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e6a9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e6a9-107">LID_ATTENDEE_CRITICAL_CHANGE</span><span class="sxs-lookup"><span data-stu-id="2e6a9-107">LID_ATTENDEE_CRITICAL_CHANGE</span></span>  <br/> |
|<span data-ttu-id="2e6a9-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="2e6a9-108">Property set:</span></span>  <br/> |<span data-ttu-id="2e6a9-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="2e6a9-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="2e6a9-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="2e6a9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2e6a9-111">0x00000001</span><span class="sxs-lookup"><span data-stu-id="2e6a9-111">0x00000001</span></span>  <br/> |
|<span data-ttu-id="2e6a9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e6a9-112">Data type:</span></span>  <br/> |<span data-ttu-id="2e6a9-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="2e6a9-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="2e6a9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2e6a9-114">Area:</span></span>  <br/> |<span data-ttu-id="2e6a9-115">会议</span><span class="sxs-lookup"><span data-stu-id="2e6a9-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e6a9-116">备注</span><span class="sxs-lookup"><span data-stu-id="2e6a9-116">Remarks</span></span>

<span data-ttu-id="2e6a9-117">该值必须以协调世界时与 UTC (UTC) 。</span><span class="sxs-lookup"><span data-stu-id="2e6a9-117">The value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e6a9-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e6a9-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e6a9-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e6a9-119">Protocol specifications</span></span>

<span data-ttu-id="2e6a9-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e6a9-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e6a9-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="2e6a9-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2e6a9-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e6a9-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e6a9-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2e6a9-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e6a9-124">头文件</span><span class="sxs-lookup"><span data-stu-id="2e6a9-124">Header files</span></span>

<span data-ttu-id="2e6a9-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2e6a9-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e6a9-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e6a9-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e6a9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e6a9-127">See also</span></span>



[<span data-ttu-id="2e6a9-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e6a9-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e6a9-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e6a9-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e6a9-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e6a9-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e6a9-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e6a9-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

