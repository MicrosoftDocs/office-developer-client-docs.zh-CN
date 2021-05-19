---
title: PidTagRecipientProposedEndTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientProposedEndTime
api_type:
- COM
ms.assetid: 08dc1f81-964b-4059-9167-e517391b26e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ea6d634b0e69cf6895c076815941754ba5e83a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332772"
---
# <a name="pidtagrecipientproposedendtime-canonical-property"></a><span data-ttu-id="ff770-103">PidTagRecipientProposedEndTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff770-103">PidTagRecipientProposedEndTime Canonical Property</span></span>

  
  
<span data-ttu-id="ff770-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff770-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff770-105">指示建议的会议结束时间。</span><span class="sxs-lookup"><span data-stu-id="ff770-105">Indicates a proposed end time of a meeting.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff770-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ff770-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff770-107">PR_RECIPIENT_PROPOSEDENDTIME</span><span class="sxs-lookup"><span data-stu-id="ff770-107">PR_RECIPIENT_PROPOSEDENDTIME</span></span>  <br/> |
|<span data-ttu-id="ff770-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ff770-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ff770-109">0x5FE4</span><span class="sxs-lookup"><span data-stu-id="ff770-109">0x5FE4</span></span>  <br/> |
|<span data-ttu-id="ff770-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff770-110">Data type:</span></span>  <br/> |<span data-ttu-id="ff770-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="ff770-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="ff770-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ff770-112">Area:</span></span>  <br/> |<span data-ttu-id="ff770-113">传输收件人</span><span class="sxs-lookup"><span data-stu-id="ff770-113">Transport recipient</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff770-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff770-114">Remarks</span></span>

<span data-ttu-id="ff770-115">当 **PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) 属性的值设置为 TRUE 时，此属性的值指示与会者请求设置为单个实例会议对象或异常对象的 **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="ff770-115">When the value of the **PR_RECIPIENT_PROPOSED** ([PidTagRecipientProposed](pidtagrecipientproposed-canonical-property.md)) property is set to TRUE, the value of this property indicates the value requested by the attendee to set as the value of the **dispidApptEndWhole** ([PidLidAppointmentEndWhole](pidlidappointmentendwhole-canonical-property.md)) property for the single instance meeting object or exception object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ff770-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff770-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff770-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff770-117">Protocol specifications</span></span>

<span data-ttu-id="ff770-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff770-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff770-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ff770-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff770-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff770-120">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff770-121">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ff770-121">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff770-122">头文件</span><span class="sxs-lookup"><span data-stu-id="ff770-122">Header files</span></span>

<span data-ttu-id="ff770-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff770-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff770-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff770-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="ff770-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ff770-125">Mapitags.h</span></span>
  
> <span data-ttu-id="ff770-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ff770-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff770-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff770-127">See also</span></span>



[<span data-ttu-id="ff770-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff770-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff770-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff770-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff770-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ff770-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff770-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff770-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

