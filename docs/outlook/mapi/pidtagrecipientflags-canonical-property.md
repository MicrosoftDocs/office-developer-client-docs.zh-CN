---
title: PidTagRecipientFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientFlags
api_type:
- COM
ms.assetid: 9fbe537f-b5fe-48a2-803c-653c50c82efd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7b791d75c2a76ea1a504c0d8862dd20f5365b475
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356698"
---
# <a name="pidtagrecipientflags-canonical-property"></a><span data-ttu-id="d1a8e-103">PidTagRecipientFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1a8e-103">PidTagRecipientFlags Canonical Property</span></span>

  
  
<span data-ttu-id="d1a8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1a8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1a8e-105">指定一个用于描述收件人状态的位域。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-105">Specifies a bit field that describes the recipient status.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d1a8e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d1a8e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d1a8e-107">PR_RECIPIENT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d1a8e-107">PR_RECIPIENT_FLAGS</span></span>  <br/> |
|<span data-ttu-id="d1a8e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d1a8e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d1a8e-109">0x5FFD</span><span class="sxs-lookup"><span data-stu-id="d1a8e-109">0x5FFD</span></span>  <br/> |
|<span data-ttu-id="d1a8e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d1a8e-110">Data type:</span></span>  <br/> |<span data-ttu-id="d1a8e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d1a8e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d1a8e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d1a8e-112">Area:</span></span>  <br/> |<span data-ttu-id="d1a8e-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="d1a8e-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1a8e-114">注解</span><span class="sxs-lookup"><span data-stu-id="d1a8e-114">Remarks</span></span>

<span data-ttu-id="d1a8e-115">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-115">This property is not required.</span></span> <span data-ttu-id="d1a8e-116">以下是可以设置的单个标志。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-116">The following are the individual flags that can be set.</span></span>
  
|<span data-ttu-id="d1a8e-117">**Value**</span><span class="sxs-lookup"><span data-stu-id="d1a8e-117">**Value**</span></span>|<span data-ttu-id="d1a8e-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="d1a8e-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1a8e-119">S (recipSendable, 0x00000001)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-119">S (recipSendable, 0x00000001)</span></span>  <br/> |<span data-ttu-id="d1a8e-120">收件人是**可发送**的与会者。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-120">The recipient is a **Sendable** Attendee.</span></span> <span data-ttu-id="d1a8e-121">此标志仅在**dispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) 属性中使用。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-121">This flag is only used in the **dispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) property.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-122">O (recipOrganizer, 0x0000002)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-122">O (recipOrganizer, 0x0000002)</span></span>  <br/> |<span data-ttu-id="d1a8e-123">在其上设置此标志的**RecipientRow**代表会议组织者。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-123">The **RecipientRow** on which this flag is set represents the meeting Organizer.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-124">ER (recipExceptionalResponse, 0x00000010)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-124">ER (recipExceptionalResponse, 0x00000010)</span></span>  <br/> |<span data-ttu-id="d1a8e-125">指示与会者为此**RecipientRow**所驻留的异常提供响应。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-125">Indicates that the attendee gave a response for the exception on which this **RecipientRow** resides.</span></span> <span data-ttu-id="d1a8e-126">此标志仅用于组织者的会议对象的异常嵌入邮件对象的**RecipientRow** 。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-126">This flag is only used in a **RecipientRow** of an exception embedded message object of the organizer's meeting object.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-127">ED (recipExceptionalDeleted, 0x00000020)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-127">ED (recipExceptionalDeleted, 0x00000020)</span></span>  <br/> |<span data-ttu-id="d1a8e-128">指示尽管**RecipientRow**存在, 但应将其视为相应的收件人不是。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-128">Indicates that although the **RecipientRow** exists, it should be treated as if the corresponding recipient does not.</span></span> <span data-ttu-id="d1a8e-129">此标志仅用于组织者的会议对象的异常嵌入邮件对象的**RecipientRow** 。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-129">This flag is only used in a **RecipientRow** of an exception embedded message object of the organizer's meeting object.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-130">X (reserved, 0x00000040)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-130">X (reserved, 0x00000040)</span></span>  <br/> |<span data-ttu-id="d1a8e-131">不得设置。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-131">Must not be set.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-132">X (reserved, 0x00000080)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-132">X (reserved, 0x00000080)</span></span>  <br/> |<span data-ttu-id="d1a8e-133">不得设置。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-133">Must not be set.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-134">G (recipOriginal, 0x00000100)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-134">G (recipOriginal, 0x00000100)</span></span>  <br/> |<span data-ttu-id="d1a8e-135">指示收件人是原始与会者。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-135">Indicates the recipient is an original attendee.</span></span> <span data-ttu-id="d1a8e-136">此标志仅在**dispidApptUnsendableRecips**属性中使用。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-136">This flag is only used in the **dispidApptUnsendableRecips** property.</span></span>  <br/> |
|<span data-ttu-id="d1a8e-137">X (reserved, 0x00000200)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-137">X (reserved, 0x00000200)</span></span>  <br/> |<span data-ttu-id="d1a8e-138">保留。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-138">Reserved.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="d1a8e-139">相关资源</span><span class="sxs-lookup"><span data-stu-id="d1a8e-139">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d1a8e-140">协议规范</span><span class="sxs-lookup"><span data-stu-id="d1a8e-140">Protocol specifications</span></span>

<span data-ttu-id="d1a8e-141">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-141">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1a8e-142">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-142">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d1a8e-143">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d1a8e-143">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d1a8e-144">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-144">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d1a8e-145">头文件</span><span class="sxs-lookup"><span data-stu-id="d1a8e-145">Header files</span></span>

<span data-ttu-id="d1a8e-146">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d1a8e-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="d1a8e-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="d1a8e-148">Mapitags</span><span class="sxs-lookup"><span data-stu-id="d1a8e-148">Mapitags.h</span></span>
  
> <span data-ttu-id="d1a8e-149">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d1a8e-149">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d1a8e-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1a8e-150">See also</span></span>



[<span data-ttu-id="d1a8e-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d1a8e-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d1a8e-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d1a8e-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d1a8e-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d1a8e-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d1a8e-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d1a8e-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

