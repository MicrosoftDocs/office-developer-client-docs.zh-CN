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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dac2cb1d40fadbe0cad67b144891b0ece54aae9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341109"
---
# <a name="pidtagrecipientreassignmentprohibited-canonical-property"></a><span data-ttu-id="fe47b-103">PidTagRecipientReassignmentProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe47b-103">PidTagRecipientReassignmentProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="fe47b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe47b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe47b-105">指定在转发邮件时是否禁止为电子邮件添加其他收件人。</span><span class="sxs-lookup"><span data-stu-id="fe47b-105">Specifies whether adding additional recipients, when forwarding the message, is prohibited for the email message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fe47b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fe47b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fe47b-107">PR_RECIPIENT_REASSIGNMENT_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="fe47b-107">PR_RECIPIENT_REASSIGNMENT_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="fe47b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fe47b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fe47b-109">0x002B</span><span class="sxs-lookup"><span data-stu-id="fe47b-109">0x002B</span></span>  <br/> |
|<span data-ttu-id="fe47b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fe47b-110">Data type:</span></span>  <br/> |<span data-ttu-id="fe47b-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="fe47b-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="fe47b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fe47b-112">Area:</span></span>  <br/> |<span data-ttu-id="fe47b-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="fe47b-113">MAPI Envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe47b-114">备注</span><span class="sxs-lookup"><span data-stu-id="fe47b-114">Remarks</span></span>

<span data-ttu-id="fe47b-115">此属性根据电子邮件的默认值PR_SENSITIVITY ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 值。 </span><span class="sxs-lookup"><span data-stu-id="fe47b-115">This property is set based on the email message's **PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) value.</span></span> <span data-ttu-id="fe47b-116">如果 **PR_SENSITIVITY** 设置为"0x00000000" (普通) 或"0x00000003" (机密) ，则必须将此属性设置为"0x00"，或不存在允许向电子邮件添加其他或不同收件人的含义。</span><span class="sxs-lookup"><span data-stu-id="fe47b-116">If **PR_SENSITIVITY** is set to "0x00000000" (normal) or "0x00000003" (confidential), this property must be set to "0x00" or absent meaning that adding additional or different recipients to the email message is allowed.</span></span> <span data-ttu-id="fe47b-117">如果电子邮件对象的 **PR_SENSITIVITY** 设置为"0x00000001" (个人) 或"0x00000002" (专用) ，则必须将此属性设置为"0x01"以防止通过转发添加此电子邮件的其他或不同收件人。</span><span class="sxs-lookup"><span data-stu-id="fe47b-117">If the email object's **PR_SENSITIVITY** is set to "0x00000001" (personal) or "0x00000002" (private), this property must be set "0x01" to prevent adding additional or different recipients of this email through forwarding.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="fe47b-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="fe47b-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fe47b-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="fe47b-119">Protocol specifications</span></span>

<span data-ttu-id="fe47b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe47b-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fe47b-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="fe47b-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fe47b-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe47b-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fe47b-123">指定允许对电子邮件执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="fe47b-123">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fe47b-124">头文件</span><span class="sxs-lookup"><span data-stu-id="fe47b-124">Header files</span></span>

<span data-ttu-id="fe47b-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fe47b-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="fe47b-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fe47b-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="fe47b-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fe47b-127">Mapitags.h</span></span>
  
> <span data-ttu-id="fe47b-128">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fe47b-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fe47b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe47b-129">See also</span></span>



[<span data-ttu-id="fe47b-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fe47b-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fe47b-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe47b-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fe47b-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fe47b-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fe47b-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fe47b-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

