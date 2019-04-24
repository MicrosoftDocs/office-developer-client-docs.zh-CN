---
title: PidLidAppointmentAuxiliaryFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentAuxiliaryFlags
api_type:
- COM
ms.assetid: 56c64e23-4a99-4f80-ba06-dfae2a5fe961
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4414ae866dece0654131d1575fe699676892709f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345428"
---
# <a name="pidlidappointmentauxiliaryflags-canonical-property"></a><span data-ttu-id="cea39-103">PidLidAppointmentAuxiliaryFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="cea39-103">PidLidAppointmentAuxiliaryFlags Canonical Property</span></span>

  
  
<span data-ttu-id="cea39-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cea39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cea39-105">指定一个用于描述对象的辅助状态的位域。</span><span class="sxs-lookup"><span data-stu-id="cea39-105">Specifies a bit field that describes the auxiliary state of the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cea39-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cea39-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cea39-107">dispidApptAuxFlags</span><span class="sxs-lookup"><span data-stu-id="cea39-107">dispidApptAuxFlags</span></span>  <br/> |
|<span data-ttu-id="cea39-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="cea39-108">Property set:</span></span>  <br/> |<span data-ttu-id="cea39-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="cea39-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="cea39-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="cea39-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cea39-111">0x00008207</span><span class="sxs-lookup"><span data-stu-id="cea39-111">0x00008207</span></span>  <br/> |
|<span data-ttu-id="cea39-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cea39-112">Data type:</span></span>  <br/> |<span data-ttu-id="cea39-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="cea39-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="cea39-114">区域：</span><span class="sxs-lookup"><span data-stu-id="cea39-114">Area:</span></span>  <br/> |<span data-ttu-id="cea39-115">会议</span><span class="sxs-lookup"><span data-stu-id="cea39-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cea39-116">注解</span><span class="sxs-lookup"><span data-stu-id="cea39-116">Remarks</span></span>

<span data-ttu-id="cea39-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="cea39-117">This property is not required.</span></span> <span data-ttu-id="cea39-118">以下是可以设置的各个标志。</span><span class="sxs-lookup"><span data-stu-id="cea39-118">Below are the individual flags that can be set.</span></span>
  
<span data-ttu-id="cea39-119">C (auxApptFlagCopied, 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="cea39-119">C (auxApptFlagCopied, 0x00000001)</span></span>
  
> <span data-ttu-id="cea39-120">此标志指示 calendar 对象是从另一个 "日历" 文件夹中复制的。</span><span class="sxs-lookup"><span data-stu-id="cea39-120">This flag indicates that the calendar object was copied from another calendar folder.</span></span>
    
<span data-ttu-id="cea39-121">R (auxApptFlagForceMtgResponse、0x00000002)</span><span class="sxs-lookup"><span data-stu-id="cea39-121">R (auxApptFlagForceMtgResponse, 0x00000002)</span></span>
  
> <span data-ttu-id="cea39-122">会议请求上的此标志表示客户端或服务器在选择响应时, 应将会议响应发送回组织者。</span><span class="sxs-lookup"><span data-stu-id="cea39-122">This flag on a meeting request indicates that the client or server should send a meeting response back to the organizer when a response is chosen.</span></span>
    
<span data-ttu-id="cea39-123">F (auxApptFlagForwarded, 0x00000004)</span><span class="sxs-lookup"><span data-stu-id="cea39-123">F (auxApptFlagForwarded, 0x00000004)</span></span>
  
> <span data-ttu-id="cea39-124">会议请求上的此标志表明它已被转发 (包括由组织者转发), 而不是来自组织者的邀请。</span><span class="sxs-lookup"><span data-stu-id="cea39-124">This flag on a meeting request indicates that it was forwarded (including being forwarded by the organizer), rather than being an invitation from the organizer.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="cea39-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="cea39-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cea39-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="cea39-126">Protocol specifications</span></span>

<span data-ttu-id="cea39-127">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cea39-127">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cea39-128">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cea39-128">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cea39-129">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cea39-129">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cea39-130">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="cea39-130">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cea39-131">头文件</span><span class="sxs-lookup"><span data-stu-id="cea39-131">Header files</span></span>

<span data-ttu-id="cea39-132">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="cea39-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="cea39-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cea39-133">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cea39-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cea39-134">See also</span></span>



[<span data-ttu-id="cea39-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cea39-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cea39-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cea39-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cea39-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cea39-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cea39-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cea39-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

