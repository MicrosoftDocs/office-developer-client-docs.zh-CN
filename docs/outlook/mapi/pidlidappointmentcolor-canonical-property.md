---
title: PidLidAppointmentColor 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentColor
api_type:
- COM
ms.assetid: 91147e85-f440-4463-850b-efc9bdbd36d1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ea0830a06f303da8243f927e4a07cc744951ca9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345435"
---
# <a name="pidlidappointmentcolor-canonical-property"></a><span data-ttu-id="a342e-103">PidLidAppointmentColor 规范属性</span><span class="sxs-lookup"><span data-stu-id="a342e-103">PidLidAppointmentColor Canonical Property</span></span>

  
  
<span data-ttu-id="a342e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a342e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a342e-105">指定在显示日历时要使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="a342e-105">Specifies the color to use when displaying the calendar.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a342e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a342e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a342e-107">dispidApptColor</span><span class="sxs-lookup"><span data-stu-id="a342e-107">dispidApptColor</span></span>  <br/> |
|<span data-ttu-id="a342e-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="a342e-108">Property set:</span></span>  <br/> |<span data-ttu-id="a342e-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="a342e-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="a342e-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="a342e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="a342e-111">0x00008214</span><span class="sxs-lookup"><span data-stu-id="a342e-111">0x00008214</span></span>  <br/> |
|<span data-ttu-id="a342e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a342e-112">Data type:</span></span>  <br/> |<span data-ttu-id="a342e-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a342e-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a342e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="a342e-114">Area:</span></span>  <br/> |<span data-ttu-id="a342e-115">日历</span><span class="sxs-lookup"><span data-stu-id="a342e-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a342e-116">注解</span><span class="sxs-lookup"><span data-stu-id="a342e-116">Remarks</span></span>

<span data-ttu-id="a342e-117">此属性指定在显示日历时要使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="a342e-117">This property specifies the color to use when displaying the calendar.</span></span> <span data-ttu-id="a342e-118">客户端或服务器应设置此值以实现与旧客户端的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="a342e-118">A client or server should set this value for backward compatibility with older clients.</span></span> <span data-ttu-id="a342e-119">它可能改为根据[[OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)中指定的**关键字**([PidNameKeywords](pidnamekeywords-canonical-property.md)) 属性的值显示日历。</span><span class="sxs-lookup"><span data-stu-id="a342e-119">It may instead display the calendar based on the value of the **Keywords** ([PidNameKeywords](pidnamekeywords-canonical-property.md)) property as specified in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span> <span data-ttu-id="a342e-120">如果设置, 则值必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="a342e-120">When set, the value must be one of the following.</span></span>
  
|<span data-ttu-id="a342e-121">**值**</span><span class="sxs-lookup"><span data-stu-id="a342e-121">**Value**</span></span>|<span data-ttu-id="a342e-122">**Color**</span><span class="sxs-lookup"><span data-stu-id="a342e-122">**Color**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a342e-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="a342e-123">0x00000000</span></span>  <br/> |<span data-ttu-id="a342e-124">无</span><span class="sxs-lookup"><span data-stu-id="a342e-124">None</span></span>  <br/> |
|<span data-ttu-id="a342e-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="a342e-125">0x00000001</span></span>  <br/> |<span data-ttu-id="a342e-126">红色</span><span class="sxs-lookup"><span data-stu-id="a342e-126">Red</span></span>  <br/> |
|<span data-ttu-id="a342e-127">0x00000002</span><span class="sxs-lookup"><span data-stu-id="a342e-127">0x00000002</span></span>  <br/> |<span data-ttu-id="a342e-128">蓝色</span><span class="sxs-lookup"><span data-stu-id="a342e-128">Blue</span></span>  <br/> |
|<span data-ttu-id="a342e-129">0x00000003</span><span class="sxs-lookup"><span data-stu-id="a342e-129">0x00000003</span></span>  <br/> |<span data-ttu-id="a342e-130">绿色</span><span class="sxs-lookup"><span data-stu-id="a342e-130">Green</span></span>  <br/> |
|<span data-ttu-id="a342e-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="a342e-131">0x00000004</span></span>  <br/> |<span data-ttu-id="a342e-132">灰色</span><span class="sxs-lookup"><span data-stu-id="a342e-132">Grey</span></span>  <br/> |
|<span data-ttu-id="a342e-133">0x00000005</span><span class="sxs-lookup"><span data-stu-id="a342e-133">0x00000005</span></span>  <br/> |<span data-ttu-id="a342e-134">橙色</span><span class="sxs-lookup"><span data-stu-id="a342e-134">Orange</span></span>  <br/> |
|<span data-ttu-id="a342e-135">0x00000006</span><span class="sxs-lookup"><span data-stu-id="a342e-135">0x00000006</span></span>  <br/> |<span data-ttu-id="a342e-136">蓝绿</span><span class="sxs-lookup"><span data-stu-id="a342e-136">Cyan</span></span>  <br/> |
|<span data-ttu-id="a342e-137">0x00000007</span><span class="sxs-lookup"><span data-stu-id="a342e-137">0x00000007</span></span>  <br/> |<span data-ttu-id="a342e-138">橄榄色</span><span class="sxs-lookup"><span data-stu-id="a342e-138">Olive</span></span>  <br/> |
|<span data-ttu-id="a342e-139">0x00000008</span><span class="sxs-lookup"><span data-stu-id="a342e-139">0x00000008</span></span>  <br/> |<span data-ttu-id="a342e-140">紫色</span><span class="sxs-lookup"><span data-stu-id="a342e-140">Purple</span></span>  <br/> |
|<span data-ttu-id="a342e-141">0x00000009</span><span class="sxs-lookup"><span data-stu-id="a342e-141">0x00000009</span></span>  <br/> |<span data-ttu-id="a342e-142">青色</span><span class="sxs-lookup"><span data-stu-id="a342e-142">Teal</span></span>  <br/> |
|<span data-ttu-id="a342e-143">0x0000000A</span><span class="sxs-lookup"><span data-stu-id="a342e-143">0x0000000A</span></span>  <br/> |<span data-ttu-id="a342e-144">黄色</span><span class="sxs-lookup"><span data-stu-id="a342e-144">Yellow</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="a342e-145">相关资源</span><span class="sxs-lookup"><span data-stu-id="a342e-145">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a342e-146">协议规范</span><span class="sxs-lookup"><span data-stu-id="a342e-146">Protocol specifications</span></span>

<span data-ttu-id="a342e-147">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a342e-147">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a342e-148">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a342e-148">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a342e-149">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a342e-149">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a342e-150">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a342e-150">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a342e-151">头文件</span><span class="sxs-lookup"><span data-stu-id="a342e-151">Header files</span></span>

<span data-ttu-id="a342e-152">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a342e-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="a342e-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a342e-153">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a342e-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a342e-154">See also</span></span>



[<span data-ttu-id="a342e-155">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a342e-155">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a342e-156">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a342e-156">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a342e-157">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a342e-157">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a342e-158">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a342e-158">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

