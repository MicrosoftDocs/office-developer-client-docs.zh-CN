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
ms.openlocfilehash: a00517dfa87d739f19c19d0b02ab8437cae698d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359064"
---
# <a name="pidlidoldwhenendwhole-canonical-property"></a><span data-ttu-id="48dd8-103">PidLidOldWhenEndWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="48dd8-103">PidLidOldWhenEndWhole Canonical Property</span></span>

  
  
<span data-ttu-id="48dd8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48dd8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48dd8-105">指示会议更新前的**dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的原始值。</span><span class="sxs-lookup"><span data-stu-id="48dd8-105">Indicates the original value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property before a meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="48dd8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="48dd8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48dd8-107">dispidOldWhenEndWhole</span><span class="sxs-lookup"><span data-stu-id="48dd8-107">dispidOldWhenEndWhole</span></span>  <br/> |
|<span data-ttu-id="48dd8-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="48dd8-108">Property set:</span></span>  <br/> |<span data-ttu-id="48dd8-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="48dd8-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="48dd8-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="48dd8-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="48dd8-111">0x0000002A</span><span class="sxs-lookup"><span data-stu-id="48dd8-111">0x0000002A</span></span>  <br/> |
|<span data-ttu-id="48dd8-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48dd8-112">Data type:</span></span>  <br/> |<span data-ttu-id="48dd8-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="48dd8-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="48dd8-114">区域：</span><span class="sxs-lookup"><span data-stu-id="48dd8-114">Area:</span></span>  <br/> |<span data-ttu-id="48dd8-115">会议</span><span class="sxs-lookup"><span data-stu-id="48dd8-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="48dd8-116">注解</span><span class="sxs-lookup"><span data-stu-id="48dd8-116">Remarks</span></span>

<span data-ttu-id="48dd8-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="48dd8-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="48dd8-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="48dd8-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="48dd8-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="48dd8-119">Protocol specifications</span></span>

<span data-ttu-id="48dd8-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48dd8-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48dd8-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="48dd8-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="48dd8-122">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48dd8-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48dd8-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="48dd8-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="48dd8-124">头文件</span><span class="sxs-lookup"><span data-stu-id="48dd8-124">Header files</span></span>

<span data-ttu-id="48dd8-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="48dd8-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="48dd8-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48dd8-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48dd8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48dd8-127">See also</span></span>



[<span data-ttu-id="48dd8-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48dd8-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48dd8-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48dd8-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48dd8-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="48dd8-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48dd8-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48dd8-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

