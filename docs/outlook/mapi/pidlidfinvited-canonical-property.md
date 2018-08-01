---
title: PidLidFInvited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFInvited
api_type:
- COM
ms.assetid: ca1ea5ec-20d5-4b70-95de-c2246a10beae
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 409fc2e01b103378eb0df1bdd06ee8b5647148bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776839"
---
# <a name="pidlidfinvited-canonical-property"></a><span data-ttu-id="cc563-103">PidLidFInvited 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc563-103">PidLidFInvited Canonical Property</span></span>

  
  
<span data-ttu-id="cc563-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cc563-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cc563-105">指示已发送邀请以代表此会议的会议。</span><span class="sxs-lookup"><span data-stu-id="cc563-105">Indicates whether or not invitations have been sent for the meeting that this meeting represents.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc563-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cc563-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cc563-107">dispidFInvited</span><span class="sxs-lookup"><span data-stu-id="cc563-107">dispidFInvited</span></span>  <br/> |
|<span data-ttu-id="cc563-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cc563-108">Property set:</span></span>  <br/> |<span data-ttu-id="cc563-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="cc563-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="cc563-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cc563-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cc563-111">0x00008229</span><span class="sxs-lookup"><span data-stu-id="cc563-111">0x00008229</span></span>  <br/> |
|<span data-ttu-id="cc563-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cc563-112">Data type:</span></span>  <br/> |<span data-ttu-id="cc563-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="cc563-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="cc563-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cc563-114">Area:</span></span>  <br/> |<span data-ttu-id="cc563-115">会议</span><span class="sxs-lookup"><span data-stu-id="cc563-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc563-116">说明</span><span class="sxs-lookup"><span data-stu-id="cc563-116">Remarks</span></span>

<span data-ttu-id="cc563-117">值为 FALSE 或不存在此属性，指示已从不发送会议请求。</span><span class="sxs-lookup"><span data-stu-id="cc563-117">A value of FALSE, or the absence of this property, indicates that a meeting request has never been sent.</span></span> <span data-ttu-id="cc563-118">TRUE 表示已发送会议请求。</span><span class="sxs-lookup"><span data-stu-id="cc563-118">A value of TRUE indicates that a meeting request has been sent.</span></span> <span data-ttu-id="cc563-119">一旦会议情况下，此值设置为 TRUE，则必须不能更改。</span><span class="sxs-lookup"><span data-stu-id="cc563-119">Once this value is set to TRUE on a meeting, it must not be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cc563-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="cc563-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cc563-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="cc563-121">Protocol specifications</span></span>

<span data-ttu-id="cc563-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc563-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc563-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cc563-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cc563-124">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc563-124">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc563-125">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="cc563-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cc563-126">头文件</span><span class="sxs-lookup"><span data-stu-id="cc563-126">Header files</span></span>

<span data-ttu-id="cc563-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cc563-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="cc563-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cc563-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cc563-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc563-129">See also</span></span>



[<span data-ttu-id="cc563-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cc563-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cc563-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc563-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cc563-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cc563-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cc563-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cc563-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

