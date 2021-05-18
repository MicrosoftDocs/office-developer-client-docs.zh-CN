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
ms.openlocfilehash: 3a87beaa3873b5ccb449e5b1497262bad5bf1497
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282366"
---
# <a name="pidtagjunkaddrecipientstosafesenderslist-canonical-property"></a><span data-ttu-id="f24a2-103">PidTagJunkAddRecipientsToSafeSendersList 规范属性</span><span class="sxs-lookup"><span data-stu-id="f24a2-103">PidTagJunkAddRecipientsToSafeSendersList Canonical Property</span></span>

  
  
<span data-ttu-id="f24a2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f24a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f24a2-105">指示是否将邮件收件人添加到安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="f24a2-105">Indicates whether or not the mail recipients are to be added to the safe senders list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f24a2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f24a2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f24a2-107">PR_JUNK_ADD_RECIPS_TO_SSL</span><span class="sxs-lookup"><span data-stu-id="f24a2-107">PR_JUNK_ADD_RECIPS_TO_SSL</span></span>  <br/> |
|<span data-ttu-id="f24a2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f24a2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f24a2-109">0x6103</span><span class="sxs-lookup"><span data-stu-id="f24a2-109">0x6103</span></span>  <br/> |
|<span data-ttu-id="f24a2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f24a2-110">Data type:</span></span>  <br/> |<span data-ttu-id="f24a2-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f24a2-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f24a2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f24a2-112">Area:</span></span>  <br/> |<span data-ttu-id="f24a2-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f24a2-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f24a2-114">备注</span><span class="sxs-lookup"><span data-stu-id="f24a2-114">Remarks</span></span>

<span data-ttu-id="f24a2-115">如果存在，此属性必须设置为 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="f24a2-115">If present, this property must be set to 0 or 1.</span></span> <span data-ttu-id="f24a2-116">值 1 指示邮件收件人将添加到安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="f24a2-116">A value of 1 indicates that the mail recipients are to be added to the safe senders list.</span></span> <span data-ttu-id="f24a2-117">值 0 表示不会将邮件收件人添加到安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="f24a2-117">A value of 0 indicates that the mail recipients are not to be added to the safe senders list.</span></span>
  
<span data-ttu-id="f24a2-118">如果此属性存在值 1，则必须将电子邮件收件人的 SMTP 地址添加到垃圾邮件规则条件的受信任的发件人子句中。</span><span class="sxs-lookup"><span data-stu-id="f24a2-118">If this property is present with a value of 1, the SMTP addresses of the email recipients must be added to trusted senders clause of the Junk E-Mail Rule condition.</span></span> <span data-ttu-id="f24a2-119">如果此属性为 0，则无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="f24a2-119">If this property is 0, no action is required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f24a2-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="f24a2-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f24a2-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="f24a2-121">Protocol specifications</span></span>

<span data-ttu-id="f24a2-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f24a2-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f24a2-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="f24a2-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f24a2-124">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f24a2-124">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f24a2-125">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="f24a2-125">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f24a2-126">头文件</span><span class="sxs-lookup"><span data-stu-id="f24a2-126">Header files</span></span>

<span data-ttu-id="f24a2-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f24a2-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="f24a2-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f24a2-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="f24a2-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f24a2-129">Mapitags.h</span></span>
  
> <span data-ttu-id="f24a2-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f24a2-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f24a2-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f24a2-131">See also</span></span>



[<span data-ttu-id="f24a2-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f24a2-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f24a2-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f24a2-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f24a2-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f24a2-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f24a2-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f24a2-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

