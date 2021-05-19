---
title: PidLidOldWhenStartWhole 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOldWhenStartWhole
api_type:
- COM
ms.assetid: 73064a22-68bf-4d3f-91f5-1eec807debf8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7483d887a7033b8137ce9861ff0d9513fe32904
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358000"
---
# <a name="pidlidoldwhenstartwhole-canonical-property"></a><span data-ttu-id="56919-103">PidLidOldWhenStartWhole 规范属性</span><span class="sxs-lookup"><span data-stu-id="56919-103">PidLidOldWhenStartWhole Canonical Property</span></span>

  
  
<span data-ttu-id="56919-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56919-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56919-105">指示会议更新前 **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) 属性的原始值。</span><span class="sxs-lookup"><span data-stu-id="56919-105">Indicates the original value of the **dispidApptStartWhole** ([PidLidAppointmentStartWhole](pidlidappointmentstartwhole-canonical-property.md)) property before a meeting update.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="56919-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="56919-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="56919-107">dispidOldWhenStartWhole</span><span class="sxs-lookup"><span data-stu-id="56919-107">dispidOldWhenStartWhole</span></span>  <br/> |
|<span data-ttu-id="56919-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="56919-108">Property set:</span></span>  <br/> |<span data-ttu-id="56919-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="56919-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="56919-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="56919-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="56919-111">0x00000029</span><span class="sxs-lookup"><span data-stu-id="56919-111">0x00000029</span></span>  <br/> |
|<span data-ttu-id="56919-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="56919-112">Data type:</span></span>  <br/> |<span data-ttu-id="56919-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="56919-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="56919-114">区域：</span><span class="sxs-lookup"><span data-stu-id="56919-114">Area:</span></span>  <br/> |<span data-ttu-id="56919-115">会议</span><span class="sxs-lookup"><span data-stu-id="56919-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="56919-116">备注</span><span class="sxs-lookup"><span data-stu-id="56919-116">Remarks</span></span>

<span data-ttu-id="56919-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="56919-117">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="56919-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="56919-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="56919-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="56919-119">Protocol specifications</span></span>

<span data-ttu-id="56919-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56919-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56919-121">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="56919-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="56919-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="56919-122">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="56919-123">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="56919-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="56919-124">头文件</span><span class="sxs-lookup"><span data-stu-id="56919-124">Header files</span></span>

<span data-ttu-id="56919-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="56919-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="56919-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="56919-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="56919-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56919-127">See also</span></span>



[<span data-ttu-id="56919-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="56919-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="56919-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="56919-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="56919-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="56919-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="56919-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="56919-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

