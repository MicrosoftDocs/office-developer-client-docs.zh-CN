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
ms.openlocfilehash: cac9c735403e6cb65dfe3111a2246a8387339339
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776584"
---
# <a name="pidlidappointmentauxiliaryflags-canonical-property"></a><span data-ttu-id="b35a6-103">PidLidAppointmentAuxiliaryFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="b35a6-103">PidLidAppointmentAuxiliaryFlags Canonical Property</span></span>

  
  
<span data-ttu-id="b35a6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b35a6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b35a6-105">指定的描述对象的辅助状态位字段。</span><span class="sxs-lookup"><span data-stu-id="b35a6-105">Specifies a bit field that describes the auxiliary state of the object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b35a6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b35a6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b35a6-107">dispidApptAuxFlags</span><span class="sxs-lookup"><span data-stu-id="b35a6-107">dispidApptAuxFlags</span></span>  <br/> |
|<span data-ttu-id="b35a6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="b35a6-108">Property set:</span></span>  <br/> |<span data-ttu-id="b35a6-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="b35a6-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="b35a6-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="b35a6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="b35a6-111">0x00008207</span><span class="sxs-lookup"><span data-stu-id="b35a6-111">0x00008207</span></span>  <br/> |
|<span data-ttu-id="b35a6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b35a6-112">Data type:</span></span>  <br/> |<span data-ttu-id="b35a6-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="b35a6-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="b35a6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="b35a6-114">Area:</span></span>  <br/> |<span data-ttu-id="b35a6-115">会议</span><span class="sxs-lookup"><span data-stu-id="b35a6-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b35a6-116">说明</span><span class="sxs-lookup"><span data-stu-id="b35a6-116">Remarks</span></span>

<span data-ttu-id="b35a6-117">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b35a6-117">This property is not required.</span></span> <span data-ttu-id="b35a6-118">下面是可以设置的单个标记。</span><span class="sxs-lookup"><span data-stu-id="b35a6-118">Below are the individual flags that can be set.</span></span>
  
<span data-ttu-id="b35a6-119">C (auxApptFlagCopied，0x00000001)</span><span class="sxs-lookup"><span data-stu-id="b35a6-119">C (auxApptFlagCopied, 0x00000001)</span></span>
  
> <span data-ttu-id="b35a6-120">此标志指示 calendar 对象已复制从另一个日历文件夹。</span><span class="sxs-lookup"><span data-stu-id="b35a6-120">This flag indicates that the calendar object was copied from another calendar folder.</span></span>
    
<span data-ttu-id="b35a6-121">R (auxApptFlagForceMtgResponse，0x00000002:uc)</span><span class="sxs-lookup"><span data-stu-id="b35a6-121">R (auxApptFlagForceMtgResponse, 0x00000002)</span></span>
  
> <span data-ttu-id="b35a6-122">在会议请求此标志指示客户端或服务器应发送回组织者的会议响应，如果选择响应。</span><span class="sxs-lookup"><span data-stu-id="b35a6-122">This flag on a meeting request indicates that the client or server should send a meeting response back to the organizer when a response is chosen.</span></span>
    
<span data-ttu-id="b35a6-123">F (auxApptFlagForwarded，0x00000004)</span><span class="sxs-lookup"><span data-stu-id="b35a6-123">F (auxApptFlagForwarded, 0x00000004)</span></span>
  
> <span data-ttu-id="b35a6-124">在会议请求此标志指示它已转发 （包括由组织者转发的），而不是组织者的邀请。</span><span class="sxs-lookup"><span data-stu-id="b35a6-124">This flag on a meeting request indicates that it was forwarded (including being forwarded by the organizer), rather than being an invitation from the organizer.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="b35a6-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="b35a6-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b35a6-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="b35a6-126">Protocol specifications</span></span>

<span data-ttu-id="b35a6-127">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35a6-127">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35a6-128">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b35a6-128">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b35a6-129">[[MS OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b35a6-129">[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b35a6-130">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="b35a6-130">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b35a6-131">头文件</span><span class="sxs-lookup"><span data-stu-id="b35a6-131">Header files</span></span>

<span data-ttu-id="b35a6-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b35a6-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="b35a6-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b35a6-133">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b35a6-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b35a6-134">See also</span></span>



[<span data-ttu-id="b35a6-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b35a6-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b35a6-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b35a6-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b35a6-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b35a6-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b35a6-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b35a6-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

