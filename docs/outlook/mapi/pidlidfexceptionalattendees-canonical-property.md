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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68ad6bd888594d09ab8e1dac050f8181341f7ee4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570778"
---
# <a name="pidlidfexceptionalattendees-canonical-property"></a><span data-ttu-id="4c692-103">PidLidFExceptionalAttendees 规范属性</span><span class="sxs-lookup"><span data-stu-id="4c692-103">PidLidFExceptionalAttendees Canonical Property</span></span>

  
  
<span data-ttu-id="4c692-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c692-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c692-105">指示此属性是定期 calendar 对象具有一个或多个异常，并至少一个嵌入的异常消息具有至少一个 RecipientRow。</span><span class="sxs-lookup"><span data-stu-id="4c692-105">Indicates whether this property is a recurring calendar object with one or more exceptions, and at least one of the exception embedded messages has at least one RecipientRow.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4c692-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4c692-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4c692-107">dispidFExceptionalAttendees</span><span class="sxs-lookup"><span data-stu-id="4c692-107">dispidFExceptionalAttendees</span></span>  <br/> |
|<span data-ttu-id="4c692-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="4c692-108">Property set:</span></span>  <br/> |<span data-ttu-id="4c692-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="4c692-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="4c692-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="4c692-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="4c692-111">0x0000822B</span><span class="sxs-lookup"><span data-stu-id="4c692-111">0x0000822B</span></span>  <br/> |
|<span data-ttu-id="4c692-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4c692-112">Data type:</span></span>  <br/> |<span data-ttu-id="4c692-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="4c692-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="4c692-114">区域：</span><span class="sxs-lookup"><span data-stu-id="4c692-114">Area:</span></span>  <br/> |<span data-ttu-id="4c692-115">会议</span><span class="sxs-lookup"><span data-stu-id="4c692-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4c692-116">注解</span><span class="sxs-lookup"><span data-stu-id="4c692-116">Remarks</span></span>

<span data-ttu-id="4c692-117">值为 FALSE 或不存在此属性表示 calendar 对象既可以具有任何异常，或无嵌入的异常消息具有 RecipientRows。</span><span class="sxs-lookup"><span data-stu-id="4c692-117">A value of FALSE, or the absence of this property, indicates that the calendar object either has no exceptions, or none of the exception embedded messages has RecipientRows.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4c692-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="4c692-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4c692-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="4c692-119">Protocol specifications</span></span>

<span data-ttu-id="4c692-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4c692-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4c692-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4c692-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4c692-122">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4c692-122">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4c692-123">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="4c692-123">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4c692-124">头文件</span><span class="sxs-lookup"><span data-stu-id="4c692-124">Header files</span></span>

<span data-ttu-id="4c692-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4c692-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="4c692-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4c692-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4c692-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c692-127">See also</span></span>



[<span data-ttu-id="4c692-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4c692-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4c692-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4c692-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4c692-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4c692-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4c692-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4c692-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

