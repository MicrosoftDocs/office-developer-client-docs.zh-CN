---
title: PidLidOldWhenEndWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOldWhenEndWhole
api_type:
- COM
ms.assetid: 788227e9-9bcf-465c-886c-746dbc665230
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f1b98b12ac573165495de6938dd4bcd7e22a084b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588459"
---
# <a name="pidlidoldwhenendwhole-canonical-property"></a><span data-ttu-id="c8175-103">PidLidOldWhenEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="c8175-103">PidLidOldWhenEndWhole Canonical Property</span></span>

  
  
<span data-ttu-id="c8175-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8175-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8175-105">指示会议更新之前的**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的原始值。</span><span class="sxs-lookup"><span data-stu-id="c8175-105">Indicates the original value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property before a meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c8175-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c8175-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c8175-107">dispidOldWhenEndWhole</span><span class="sxs-lookup"><span data-stu-id="c8175-107">dispidOldWhenEndWhole</span></span>  <br/> |
|<span data-ttu-id="c8175-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="c8175-108">Property set:</span></span>  <br/> |<span data-ttu-id="c8175-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="c8175-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="c8175-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="c8175-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="c8175-111">0x0000002A</span><span class="sxs-lookup"><span data-stu-id="c8175-111">0x0000002A</span></span>  <br/> |
|<span data-ttu-id="c8175-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c8175-112">Data type:</span></span>  <br/> |<span data-ttu-id="c8175-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="c8175-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="c8175-114">区域：</span><span class="sxs-lookup"><span data-stu-id="c8175-114">Area:</span></span>  <br/> |<span data-ttu-id="c8175-115">会议</span><span class="sxs-lookup"><span data-stu-id="c8175-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c8175-116">注解</span><span class="sxs-lookup"><span data-stu-id="c8175-116">Remarks</span></span>

<span data-ttu-id="c8175-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c8175-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c8175-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="c8175-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c8175-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="c8175-119">Protocol specifications</span></span>

<span data-ttu-id="c8175-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c8175-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c8175-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c8175-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c8175-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c8175-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c8175-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="c8175-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c8175-124">头文件</span><span class="sxs-lookup"><span data-stu-id="c8175-124">Header files</span></span>

<span data-ttu-id="c8175-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c8175-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="c8175-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c8175-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c8175-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8175-127">See also</span></span>



[<span data-ttu-id="c8175-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c8175-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c8175-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c8175-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c8175-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c8175-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c8175-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c8175-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

