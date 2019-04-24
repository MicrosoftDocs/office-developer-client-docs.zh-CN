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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7149ba5a4a0378951942df790003b6d09c1155f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358098"
---
# <a name="pidlidappointmentmessageclass-canonical-property"></a><span data-ttu-id="66ce0-103">PidLidAppointmentMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="66ce0-103">PidLidAppointmentMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="66ce0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="66ce0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="66ce0-105">指示要从会议请求生成的会议的**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="66ce0-105">Indicates the **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property of the meeting that is to be generated from the meeting request.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66ce0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="66ce0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="66ce0-107">dispidApptMessageClass</span><span class="sxs-lookup"><span data-stu-id="66ce0-107">dispidApptMessageClass</span></span>  <br/> |
|<span data-ttu-id="66ce0-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="66ce0-108">Property set:</span></span>  <br/> |<span data-ttu-id="66ce0-109">PSETID_Meeting</span><span class="sxs-lookup"><span data-stu-id="66ce0-109">PSETID_Meeting</span></span>  <br/> |
|<span data-ttu-id="66ce0-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="66ce0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="66ce0-111">0x00000024</span><span class="sxs-lookup"><span data-stu-id="66ce0-111">0x00000024</span></span>  <br/> |
|<span data-ttu-id="66ce0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="66ce0-112">Data type:</span></span>  <br/> |<span data-ttu-id="66ce0-113">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="66ce0-113">PT_TSTRING</span></span>  <br/> |
|<span data-ttu-id="66ce0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="66ce0-114">Area:</span></span>  <br/> |<span data-ttu-id="66ce0-115">会议</span><span class="sxs-lookup"><span data-stu-id="66ce0-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="66ce0-116">注解</span><span class="sxs-lookup"><span data-stu-id="66ce0-116">Remarks</span></span>

<span data-ttu-id="66ce0-117">此属性的值必须是 "IPM。约会 "或以" IPM. "作为前缀。约会 "。</span><span class="sxs-lookup"><span data-stu-id="66ce0-117">The value of this property must either be "IPM.Appointment" or be prefixed with "IPM.Appointment.".</span></span> <span data-ttu-id="66ce0-118">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="66ce0-118">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="66ce0-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="66ce0-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="66ce0-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="66ce0-120">Protocol specifications</span></span>

<span data-ttu-id="66ce0-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66ce0-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66ce0-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="66ce0-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="66ce0-123">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66ce0-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="66ce0-124">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="66ce0-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="66ce0-125">头文件</span><span class="sxs-lookup"><span data-stu-id="66ce0-125">Header files</span></span>

<span data-ttu-id="66ce0-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="66ce0-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="66ce0-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="66ce0-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="66ce0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66ce0-128">See also</span></span>



[<span data-ttu-id="66ce0-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="66ce0-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="66ce0-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="66ce0-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="66ce0-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="66ce0-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="66ce0-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="66ce0-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

