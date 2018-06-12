---
title: PidLidFExceptionalAttendees 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFExceptionalAttendees
api_type:
- COM
ms.assetid: f1f489a3-e83a-4e96-bf9a-d98bc17d29f5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7c7f654d42df7856b0e69bf276a763ccd29d1d87
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776830"
---
# <a name="pidlidfexceptionalattendees-canonical-property"></a><span data-ttu-id="dcdff-103">PidLidFExceptionalAttendees 规范属性</span><span class="sxs-lookup"><span data-stu-id="dcdff-103">PidLidFExceptionalAttendees Canonical Property</span></span>

  
  
<span data-ttu-id="dcdff-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dcdff-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dcdff-105">指示此属性是定期 calendar 对象具有一个或多个异常，并至少一个嵌入的异常消息具有至少一个 RecipientRow。</span><span class="sxs-lookup"><span data-stu-id="dcdff-105">Indicates whether this property is a recurring calendar object with one or more exceptions, and at least one of the exception embedded messages has at least one RecipientRow.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dcdff-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="dcdff-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dcdff-107">dispidFExceptionalAttendees</span><span class="sxs-lookup"><span data-stu-id="dcdff-107">dispidFExceptionalAttendees</span></span>  <br/> |
|<span data-ttu-id="dcdff-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="dcdff-108">Property set:</span></span>  <br/> |<span data-ttu-id="dcdff-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="dcdff-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="dcdff-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="dcdff-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dcdff-111">0x0000822B</span><span class="sxs-lookup"><span data-stu-id="dcdff-111">0x0000822B</span></span>  <br/> |
|<span data-ttu-id="dcdff-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dcdff-112">Data type:</span></span>  <br/> |<span data-ttu-id="dcdff-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="dcdff-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="dcdff-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dcdff-114">Area:</span></span>  <br/> |<span data-ttu-id="dcdff-115">会议</span><span class="sxs-lookup"><span data-stu-id="dcdff-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dcdff-116">备注</span><span class="sxs-lookup"><span data-stu-id="dcdff-116">Remarks</span></span>

<span data-ttu-id="dcdff-117">值为 FALSE 或不存在此属性表示 calendar 对象既可以具有任何异常，或无嵌入的异常消息具有 RecipientRows。</span><span class="sxs-lookup"><span data-stu-id="dcdff-117">A value of FALSE, or the absence of this property, indicates that the calendar object either has no exceptions, or none of the exception embedded messages has RecipientRows.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dcdff-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="dcdff-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dcdff-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="dcdff-119">Protocol specifications</span></span>

<span data-ttu-id="dcdff-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dcdff-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dcdff-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dcdff-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dcdff-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dcdff-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dcdff-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="dcdff-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dcdff-124">头文件</span><span class="sxs-lookup"><span data-stu-id="dcdff-124">Header files</span></span>

<span data-ttu-id="dcdff-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dcdff-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="dcdff-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dcdff-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dcdff-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcdff-127">See also</span></span>



[<span data-ttu-id="dcdff-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dcdff-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dcdff-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dcdff-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dcdff-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dcdff-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dcdff-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dcdff-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

