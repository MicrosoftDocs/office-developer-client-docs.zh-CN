---
title: PidTagJunkAddRecipientsToSafeSendersList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkAddRecipientsToSafeSendersList
api_type:
- HeaderDef
ms.assetid: 78543caa-e6ec-4ac7-bfdd-70c56f8fd955
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8c104af106a885f42f8063bcf5fb55d654f2688e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777776"
---
# <a name="pidtagjunkaddrecipientstosafesenderslist-canonical-property"></a><span data-ttu-id="4ac80-103">PidTagJunkAddRecipientsToSafeSendersList 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ac80-103">PidTagJunkAddRecipientsToSafeSendersList Canonical Property</span></span>

  
  
<span data-ttu-id="4ac80-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4ac80-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4ac80-105">指示要添加到安全发件人列表的邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="4ac80-105">Indicates whether or not the mail recipients are to be added to the safe senders list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4ac80-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4ac80-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4ac80-107">PR_JUNK_ADD_RECIPS_TO_SSL</span><span class="sxs-lookup"><span data-stu-id="4ac80-107">PR_JUNK_ADD_RECIPS_TO_SSL</span></span>  <br/> |
|<span data-ttu-id="4ac80-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4ac80-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4ac80-109">0x6103</span><span class="sxs-lookup"><span data-stu-id="4ac80-109">0x6103</span></span>  <br/> |
|<span data-ttu-id="4ac80-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4ac80-110">Data type:</span></span>  <br/> |<span data-ttu-id="4ac80-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="4ac80-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="4ac80-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4ac80-112">Area:</span></span>  <br/> |<span data-ttu-id="4ac80-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="4ac80-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ac80-114">说明</span><span class="sxs-lookup"><span data-stu-id="4ac80-114">Remarks</span></span>

<span data-ttu-id="4ac80-115">如果存在此参数，则此属性必须设置为 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="4ac80-115">If present, this property must be set to 0 or 1.</span></span> <span data-ttu-id="4ac80-116">1 表示邮件收件人是要添加到安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="4ac80-116">A value of 1 indicates that the mail recipients are to be added to the safe senders list.</span></span> <span data-ttu-id="4ac80-117">0 值表示邮件收件人的不是要添加到安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="4ac80-117">A value of 0 indicates that the mail recipients are not to be added to the safe senders list.</span></span>
  
<span data-ttu-id="4ac80-118">如果此属性的值为 1，则的电子邮件收件人的 SMTP 地址必须添加到受信任的发件人子句的垃圾邮件规则条件。</span><span class="sxs-lookup"><span data-stu-id="4ac80-118">If this property is present with a value of 1, the SMTP addresses of the email recipients must be added to trusted senders clause of the Junk E-Mail Rule condition.</span></span> <span data-ttu-id="4ac80-119">如果此属性为 0，则不不需要任何操作。</span><span class="sxs-lookup"><span data-stu-id="4ac80-119">If this property is 0, no action is required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4ac80-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="4ac80-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4ac80-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="4ac80-121">Protocol specifications</span></span>

<span data-ttu-id="4ac80-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ac80-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4ac80-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4ac80-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4ac80-124">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ac80-124">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4ac80-125">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="4ac80-125">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4ac80-126">头文件</span><span class="sxs-lookup"><span data-stu-id="4ac80-126">Header files</span></span>

<span data-ttu-id="4ac80-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4ac80-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="4ac80-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4ac80-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="4ac80-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4ac80-129">Mapitags.h</span></span>
  
> <span data-ttu-id="4ac80-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4ac80-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ac80-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ac80-131">See also</span></span>



[<span data-ttu-id="4ac80-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4ac80-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4ac80-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4ac80-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4ac80-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4ac80-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4ac80-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4ac80-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

