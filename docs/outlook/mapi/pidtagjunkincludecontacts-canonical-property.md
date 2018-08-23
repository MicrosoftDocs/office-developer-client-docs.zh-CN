---
title: PidTagJunkIncludeContacts 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkIncludeContacts
api_type:
- HeaderDef
ms.assetid: 25368f6c-4fba-4381-840c-ca122bd31b5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 121bba82a9ccd40a435769b5eb2d966ed60575f2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586968"
---
# <a name="pidtagjunkincludecontacts-canonical-property"></a><span data-ttu-id="370f1-103">PidTagJunkIncludeContacts 规范属性</span><span class="sxs-lookup"><span data-stu-id="370f1-103">PidTagJunkIncludeContacts Canonical Property</span></span>

  
  
<span data-ttu-id="370f1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="370f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="370f1-105">指示是否在联系人文件夹中的联系人的电子邮件地址被视为特殊相对于垃圾邮件筛选器。</span><span class="sxs-lookup"><span data-stu-id="370f1-105">Indicates whether email addresses of the contacts in the Contacts folder are treated specially with respect to the spam filter.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="370f1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="370f1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="370f1-107">PR_JUNK_INCLUDE_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="370f1-107">PR_JUNK_INCLUDE_CONTACTS</span></span>  <br/> |
|<span data-ttu-id="370f1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="370f1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="370f1-109">0x6100</span><span class="sxs-lookup"><span data-stu-id="370f1-109">0x6100</span></span>  <br/> |
|<span data-ttu-id="370f1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="370f1-110">Data type:</span></span>  <br/> |<span data-ttu-id="370f1-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="370f1-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="370f1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="370f1-112">Area:</span></span>  <br/> |<span data-ttu-id="370f1-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="370f1-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="370f1-114">注解</span><span class="sxs-lookup"><span data-stu-id="370f1-114">Remarks</span></span>

<span data-ttu-id="370f1-115">如果设置为"0x00000001"，这些电子邮件地址必须填充垃圾电子邮件规则限制的"受信任的"联系人电子邮件地址部分以便从这些地址的邮件将被视为"非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="370f1-115">If set to "0x00000001", these email addresses must populate the "trusted" contact email address portion of the Junk E-Mail Rule Restriction such that mail from these addresses is treated as "not junk".</span></span> <span data-ttu-id="370f1-116">如果设置为"0x00000000"，从联系人文件夹的电子邮件地址必须添加到垃圾邮件规则，并且该规则的一部分必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="370f1-116">If set to "0x00000000", email addresses from the Contacts folder must not be added to the Junk E-Mail Rule, and the section of the rule must be NULL.</span></span>
  
<span data-ttu-id="370f1-117">如果此属性的值为"0x00000001"并添加了的联系人如果具有未在垃圾邮件规则的受信任的联系人部分中包含的电子邮件地址，则这些电子邮件地址必须添加到限制。</span><span class="sxs-lookup"><span data-stu-id="370f1-117">If this property is present with a value of "0x00000001" and if the added contact has email addresses that are not yet included in the trusted contacts section of the Junk E-Mail Rule, those email addresses must be added to the restriction.</span></span> <span data-ttu-id="370f1-118">如果此属性为"0x00000000"，则不不需要任何操作。</span><span class="sxs-lookup"><span data-stu-id="370f1-118">If this property is "0x00000000", no action is required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="370f1-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="370f1-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="370f1-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="370f1-120">Protocol specifications</span></span>

<span data-ttu-id="370f1-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="370f1-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="370f1-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="370f1-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="370f1-123">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="370f1-123">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="370f1-124">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="370f1-124">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="370f1-125">头文件</span><span class="sxs-lookup"><span data-stu-id="370f1-125">Header files</span></span>

<span data-ttu-id="370f1-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="370f1-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="370f1-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="370f1-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="370f1-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="370f1-128">Mapitags.h</span></span>
  
> <span data-ttu-id="370f1-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="370f1-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="370f1-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="370f1-130">See also</span></span>



[<span data-ttu-id="370f1-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="370f1-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="370f1-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="370f1-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="370f1-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="370f1-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="370f1-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="370f1-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

