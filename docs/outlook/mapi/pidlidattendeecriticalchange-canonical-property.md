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
ms.openlocfilehash: f534a4738eb18519dc62cc18cfb79391ea39633b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776693"
---
# <a name="pidlidattendeecriticalchange-canonical-property"></a><span data-ttu-id="ff47e-103">PidLidAttendeeCriticalChange 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff47e-103">PidLidAttendeeCriticalChange Canonical Property</span></span>

  
  
<span data-ttu-id="ff47e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff47e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff47e-105">指定的日期和时间时发送的会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="ff47e-105">Specifies the date and time when the meeting-related object was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff47e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ff47e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff47e-107">LID_ATTENDEE_CRITICAL_CHANGE</span><span class="sxs-lookup"><span data-stu-id="ff47e-107">LID_ATTENDEE_CRITICAL_CHANGE</span></span>  <br/> |
|<span data-ttu-id="ff47e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="ff47e-108">Property set:</span></span>  <br/> |<span data-ttu-id="ff47e-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="ff47e-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="ff47e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="ff47e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ff47e-111">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ff47e-111">0x00000001</span></span>  <br/> |
|<span data-ttu-id="ff47e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff47e-112">Data type:</span></span>  <br/> |<span data-ttu-id="ff47e-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="ff47e-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="ff47e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ff47e-114">Area:</span></span>  <br/> |<span data-ttu-id="ff47e-115">会议</span><span class="sxs-lookup"><span data-stu-id="ff47e-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff47e-116">说明</span><span class="sxs-lookup"><span data-stu-id="ff47e-116">Remarks</span></span>

<span data-ttu-id="ff47e-117">必须以协调世界时 (UTC) 指定的值。</span><span class="sxs-lookup"><span data-stu-id="ff47e-117">The value must be specified in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ff47e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff47e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff47e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff47e-119">Protocol specifications</span></span>

<span data-ttu-id="ff47e-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff47e-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff47e-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ff47e-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff47e-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff47e-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff47e-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="ff47e-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff47e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="ff47e-124">Header files</span></span>

<span data-ttu-id="ff47e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff47e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff47e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff47e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff47e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff47e-127">See also</span></span>



[<span data-ttu-id="ff47e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff47e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff47e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff47e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff47e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ff47e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff47e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff47e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

