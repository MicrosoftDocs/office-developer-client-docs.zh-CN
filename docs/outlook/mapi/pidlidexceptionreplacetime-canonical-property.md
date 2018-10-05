---
title: PidLidExceptionReplaceTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidExceptionReplaceTime
api_type:
- COM
ms.assetid: c3aae4f5-7f00-45bf-b007-370041ba360e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b364fb91bda7e895b546f9a281ef14ce33b073f9
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396825"
---
# <a name="pidlidexceptionreplacetime-canonical-property"></a><span data-ttu-id="f1c74-103">PidLidExceptionReplaceTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="f1c74-103">PidLidExceptionReplaceTime Canonical Property</span></span>

  
  
<span data-ttu-id="f1c74-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1c74-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1c74-105">指定的日期和时间内定期模式的例外将替换的时间。</span><span class="sxs-lookup"><span data-stu-id="f1c74-105">Specifies the date and time within the recurrence pattern that the exception will replace.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f1c74-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f1c74-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f1c74-107">dispidExceptionReplaceTime</span><span class="sxs-lookup"><span data-stu-id="f1c74-107">dispidExceptionReplaceTime</span></span>  <br/> |
|<span data-ttu-id="f1c74-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="f1c74-108">Property set:</span></span>  <br/> |<span data-ttu-id="f1c74-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="f1c74-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="f1c74-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="f1c74-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f1c74-111">0x00008228</span><span class="sxs-lookup"><span data-stu-id="f1c74-111">0x00008228</span></span>  <br/> |
|<span data-ttu-id="f1c74-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f1c74-112">Data type:</span></span>  <br/> |<span data-ttu-id="f1c74-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="f1c74-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="f1c74-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f1c74-114">Area:</span></span>  <br/> |<span data-ttu-id="f1c74-115">日历</span><span class="sxs-lookup"><span data-stu-id="f1c74-115">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f1c74-116">说明</span><span class="sxs-lookup"><span data-stu-id="f1c74-116">Remarks</span></span>

<span data-ttu-id="f1c74-117">必须以协调世界时 (UTC) 指定的值。</span><span class="sxs-lookup"><span data-stu-id="f1c74-117">The value must be specified in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="f1c74-118">此属性允许要找的特定实例的异常附件对象。</span><span class="sxs-lookup"><span data-stu-id="f1c74-118">This property allows the exception attachment object to be found for a particular instance.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f1c74-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="f1c74-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f1c74-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="f1c74-120">Protocol specifications</span></span>

<span data-ttu-id="f1c74-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f1c74-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f1c74-122">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="f1c74-122">Provides property set definitions.</span></span>
    
<span data-ttu-id="f1c74-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f1c74-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f1c74-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="f1c74-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f1c74-125">头文件</span><span class="sxs-lookup"><span data-stu-id="f1c74-125">Header files</span></span>

<span data-ttu-id="f1c74-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f1c74-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="f1c74-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f1c74-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f1c74-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c74-128">See also</span></span>



[<span data-ttu-id="f1c74-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f1c74-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f1c74-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f1c74-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f1c74-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f1c74-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f1c74-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f1c74-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

