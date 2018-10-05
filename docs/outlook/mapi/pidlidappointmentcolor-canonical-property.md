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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399870"
---
# <a name="pidlidappointmentcolor-canonical-property"></a><span data-ttu-id="cef39-103">PidLidAppointmentColor 规范属性</span><span class="sxs-lookup"><span data-stu-id="cef39-103">PidLidAppointmentColor Canonical Property</span></span>

  
  
<span data-ttu-id="cef39-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cef39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cef39-105">指定要显示日历时使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="cef39-105">Specifies the color to use when displaying the calendar.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cef39-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cef39-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cef39-107">dispidApptColor</span><span class="sxs-lookup"><span data-stu-id="cef39-107">dispidApptColor</span></span>  <br/> |
|<span data-ttu-id="cef39-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cef39-108">Property set:</span></span>  <br/> |<span data-ttu-id="cef39-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="cef39-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="cef39-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cef39-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cef39-111">0x00008214</span><span class="sxs-lookup"><span data-stu-id="cef39-111">0x00008214</span></span>  <br/> |
|<span data-ttu-id="cef39-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cef39-112">Data type:</span></span>  <br/> |<span data-ttu-id="cef39-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cef39-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cef39-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cef39-114">Area:</span></span>  <br/> |<span data-ttu-id="cef39-115">日历</span><span class="sxs-lookup"><span data-stu-id="cef39-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cef39-116">说明</span><span class="sxs-lookup"><span data-stu-id="cef39-116">Remarks</span></span>

<span data-ttu-id="cef39-117">此属性指定要显示日历时使用的颜色。</span><span class="sxs-lookup"><span data-stu-id="cef39-117">This property specifies the color to use when displaying the calendar.</span></span> <span data-ttu-id="cef39-118">客户端或服务器应将此值与旧客户端的向后兼容性设置。</span><span class="sxs-lookup"><span data-stu-id="cef39-118">A client or server should set this value for backward compatibility with older clients.</span></span> <span data-ttu-id="cef39-119">相反，它可以显示基于**关键字**([PidNameKeywords](pidnamekeywords-canonical-property.md)) 属性中指定[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)为的值的日历。</span><span class="sxs-lookup"><span data-stu-id="cef39-119">It may instead display the calendar based on the value of the **Keywords** ([PidNameKeywords](pidnamekeywords-canonical-property.md)) property as specified in [[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx).</span></span> <span data-ttu-id="cef39-120">设置时，值必须是以下项之一。</span><span class="sxs-lookup"><span data-stu-id="cef39-120">When set, the value must be one of the following.</span></span>
  
|<span data-ttu-id="cef39-121">**值**</span><span class="sxs-lookup"><span data-stu-id="cef39-121">**Value**</span></span>|<span data-ttu-id="cef39-122">**颜色**</span><span class="sxs-lookup"><span data-stu-id="cef39-122">**Color**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cef39-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="cef39-123">0x00000000</span></span>  <br/> |<span data-ttu-id="cef39-124">无</span><span class="sxs-lookup"><span data-stu-id="cef39-124">None</span></span>  <br/> |
|<span data-ttu-id="cef39-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="cef39-125">0x00000001</span></span>  <br/> |<span data-ttu-id="cef39-126">红色</span><span class="sxs-lookup"><span data-stu-id="cef39-126">Red</span></span>  <br/> |
|<span data-ttu-id="cef39-127">0x00000002</span><span class="sxs-lookup"><span data-stu-id="cef39-127">0x00000002</span></span>  <br/> |<span data-ttu-id="cef39-128">蓝色</span><span class="sxs-lookup"><span data-stu-id="cef39-128">Blue</span></span>  <br/> |
|<span data-ttu-id="cef39-129">0x00000003</span><span class="sxs-lookup"><span data-stu-id="cef39-129">0x00000003</span></span>  <br/> |<span data-ttu-id="cef39-130">绿色</span><span class="sxs-lookup"><span data-stu-id="cef39-130">Green</span></span>  <br/> |
|<span data-ttu-id="cef39-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="cef39-131">0x00000004</span></span>  <br/> |<span data-ttu-id="cef39-132">灰色</span><span class="sxs-lookup"><span data-stu-id="cef39-132">Grey</span></span>  <br/> |
|<span data-ttu-id="cef39-133">0x00000005</span><span class="sxs-lookup"><span data-stu-id="cef39-133">0x00000005</span></span>  <br/> |<span data-ttu-id="cef39-134">橙色</span><span class="sxs-lookup"><span data-stu-id="cef39-134">Orange</span></span>  <br/> |
|<span data-ttu-id="cef39-135">0x00000006</span><span class="sxs-lookup"><span data-stu-id="cef39-135">0x00000006</span></span>  <br/> |<span data-ttu-id="cef39-136">蓝绿色</span><span class="sxs-lookup"><span data-stu-id="cef39-136">Cyan</span></span>  <br/> |
|<span data-ttu-id="cef39-137">0x00000007</span><span class="sxs-lookup"><span data-stu-id="cef39-137">0x00000007</span></span>  <br/> |<span data-ttu-id="cef39-138">橄榄绿</span><span class="sxs-lookup"><span data-stu-id="cef39-138">Olive</span></span>  <br/> |
|<span data-ttu-id="cef39-139">0x00000008</span><span class="sxs-lookup"><span data-stu-id="cef39-139">0x00000008</span></span>  <br/> |<span data-ttu-id="cef39-140">紫色</span><span class="sxs-lookup"><span data-stu-id="cef39-140">Purple</span></span>  <br/> |
|<span data-ttu-id="cef39-141">0x00000009</span><span class="sxs-lookup"><span data-stu-id="cef39-141">0x00000009</span></span>  <br/> |<span data-ttu-id="cef39-142">青色</span><span class="sxs-lookup"><span data-stu-id="cef39-142">Teal</span></span>  <br/> |
|<span data-ttu-id="cef39-143">0x0000000A</span><span class="sxs-lookup"><span data-stu-id="cef39-143">0x0000000A</span></span>  <br/> |<span data-ttu-id="cef39-144">黄色</span><span class="sxs-lookup"><span data-stu-id="cef39-144">Yellow</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="cef39-145">相关资源</span><span class="sxs-lookup"><span data-stu-id="cef39-145">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cef39-146">协议规范</span><span class="sxs-lookup"><span data-stu-id="cef39-146">Protocol specifications</span></span>

<span data-ttu-id="cef39-147">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cef39-147">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cef39-148">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cef39-148">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cef39-149">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cef39-149">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cef39-150">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="cef39-150">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cef39-151">头文件</span><span class="sxs-lookup"><span data-stu-id="cef39-151">Header files</span></span>

<span data-ttu-id="cef39-152">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cef39-152">Mapidefs.h</span></span>
  
> <span data-ttu-id="cef39-153">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cef39-153">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cef39-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cef39-154">See also</span></span>



[<span data-ttu-id="cef39-155">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cef39-155">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cef39-156">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cef39-156">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cef39-157">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cef39-157">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cef39-158">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cef39-158">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

