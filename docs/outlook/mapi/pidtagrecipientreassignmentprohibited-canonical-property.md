---
title: PidTagRecipientReassignmentProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 8636774b-1fff-4b29-bc12-4d0bd63fcba2
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0176485ca9b84260176e3be8ec9c8f42cf755cba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778160"
---
# <a name="pidtagrecipientreassignmentprohibited-canonical-property"></a><span data-ttu-id="6a137-103">PidTagRecipientReassignmentProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a137-103">PidTagRecipientReassignmentProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="6a137-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6a137-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6a137-105">指定是否添加其他收件人转发的邮件时, 禁止的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6a137-105">Specifies whether adding additional recipients, when forwarding the message, is prohibited for the email message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a137-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6a137-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a137-107">PR_RECIPIENT_REASSIGNMENT_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="6a137-107">PR_RECIPIENT_REASSIGNMENT_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="6a137-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6a137-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a137-109">0x002B</span><span class="sxs-lookup"><span data-stu-id="6a137-109">0x002B</span></span>  <br/> |
|<span data-ttu-id="6a137-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a137-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a137-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6a137-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6a137-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a137-112">Area:</span></span>  <br/> |<span data-ttu-id="6a137-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="6a137-113">MAPI Envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a137-114">备注</span><span class="sxs-lookup"><span data-stu-id="6a137-114">Remarks</span></span>

<span data-ttu-id="6a137-115">基于电子邮件的**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 值设置此属性。</span><span class="sxs-lookup"><span data-stu-id="6a137-115">This property is set based on the email message's **PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) value.</span></span> <span data-ttu-id="6a137-116">如果**PR_SENSITIVITY**设置为"0x00000000"（正常） 或"0x00000003"（机密），则此属性必须设置为"0x00"或不存在这意味着该添加允许附加的或不同的收件人添加到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6a137-116">If **PR_SENSITIVITY** is set to "0x00000000" (normal) or "0x00000003" (confidential), this property must be set to "0x00" or absent meaning that adding additional or different recipients to the email message is allowed.</span></span> <span data-ttu-id="6a137-117">如果对象的**PR_SENSITIVITY**设置为"0x00000001"（个人） 或"0x00000002:uc"（专用） 电子邮件，必须将此属性设置"0x01"以防添加其他或不同之处的转接通过此电子邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="6a137-117">If the email object's **PR_SENSITIVITY** is set to "0x00000001" (personal) or "0x00000002" (private), this property must be set "0x01" to prevent adding additional or different recipients of this email through forwarding.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6a137-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a137-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6a137-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="6a137-119">Protocol specifications</span></span>

<span data-ttu-id="6a137-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a137-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a137-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6a137-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6a137-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a137-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6a137-123">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="6a137-123">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6a137-124">头文件</span><span class="sxs-lookup"><span data-stu-id="6a137-124">Header files</span></span>

<span data-ttu-id="6a137-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6a137-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a137-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a137-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a137-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6a137-127">Mapitags.h</span></span>
  
> <span data-ttu-id="6a137-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a137-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a137-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a137-129">See also</span></span>



[<span data-ttu-id="6a137-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a137-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a137-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a137-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a137-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a137-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a137-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a137-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

