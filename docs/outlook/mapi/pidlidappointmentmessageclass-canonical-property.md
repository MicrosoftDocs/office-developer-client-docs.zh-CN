---
title: PidLidAppointmentMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentMessageClass
api_type:
- COM
ms.assetid: 8b8c8484-0cb4-4842-8b11-de42d97e0140
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8777b2119e6beefc4d69dc0babfc8672df3a468b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776599"
---
# <a name="pidlidappointmentmessageclass-canonical-property"></a><span data-ttu-id="0a3d1-103">PidLidAppointmentMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a3d1-103">PidLidAppointmentMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="0a3d1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0a3d1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0a3d1-105">指示会议的会议请求中生成的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-105">Indicates the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the meeting that is to be generated from the meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0a3d1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="0a3d1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0a3d1-107">dispidApptMessageClass</span><span class="sxs-lookup"><span data-stu-id="0a3d1-107">dispidApptMessageClass</span></span>  <br/> |
|<span data-ttu-id="0a3d1-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="0a3d1-108">Property set:</span></span>  <br/> |<span data-ttu-id="0a3d1-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="0a3d1-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="0a3d1-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="0a3d1-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0a3d1-111">0x00000024</span><span class="sxs-lookup"><span data-stu-id="0a3d1-111">0x00000024</span></span>  <br/> |
|<span data-ttu-id="0a3d1-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0a3d1-112">Data type:</span></span>  <br/> |<span data-ttu-id="0a3d1-113">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="0a3d1-113">PT_TSTRING</span></span>  <br/> |
|<span data-ttu-id="0a3d1-114">区域：</span><span class="sxs-lookup"><span data-stu-id="0a3d1-114">Area:</span></span>  <br/> |<span data-ttu-id="0a3d1-115">会议</span><span class="sxs-lookup"><span data-stu-id="0a3d1-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0a3d1-116">备注</span><span class="sxs-lookup"><span data-stu-id="0a3d1-116">Remarks</span></span>

<span data-ttu-id="0a3d1-117">此属性的值必须是"IPM。约会"或附上前缀"IPM。约会。"。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-117">The value of this property must either be "IPM.Appointment" or be prefixed with "IPM.Appointment.".</span></span> <span data-ttu-id="0a3d1-118">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-118">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0a3d1-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="0a3d1-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0a3d1-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="0a3d1-120">Protocol specifications</span></span>

<span data-ttu-id="0a3d1-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0a3d1-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0a3d1-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0a3d1-123">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0a3d1-123">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0a3d1-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0a3d1-125">头文件</span><span class="sxs-lookup"><span data-stu-id="0a3d1-125">Header files</span></span>

<span data-ttu-id="0a3d1-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0a3d1-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="0a3d1-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0a3d1-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0a3d1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a3d1-128">See also</span></span>



[<span data-ttu-id="0a3d1-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0a3d1-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0a3d1-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0a3d1-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0a3d1-131">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0a3d1-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0a3d1-132">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0a3d1-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
