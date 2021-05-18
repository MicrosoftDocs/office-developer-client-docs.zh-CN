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
ms.openlocfilehash: 7e61e98d1db1ab3acb958da353d8d22870937632
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328712"
---
# <a name="pidtagjunkincludecontacts-canonical-property"></a><span data-ttu-id="5e46e-103">PidTagJunkIncludeContacts 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e46e-103">PidTagJunkIncludeContacts Canonical Property</span></span>

  
  
<span data-ttu-id="5e46e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e46e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5e46e-105">指示是否对"联系人"文件夹中的联系人的电子邮件地址进行特殊处理，以考虑垃圾邮件筛选器。</span><span class="sxs-lookup"><span data-stu-id="5e46e-105">Indicates whether email addresses of the contacts in the Contacts folder are treated specially with respect to the spam filter.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5e46e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5e46e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5e46e-107">PR_JUNK_INCLUDE_CONTACTS</span><span class="sxs-lookup"><span data-stu-id="5e46e-107">PR_JUNK_INCLUDE_CONTACTS</span></span>  <br/> |
|<span data-ttu-id="5e46e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5e46e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5e46e-109">0x6100</span><span class="sxs-lookup"><span data-stu-id="5e46e-109">0x6100</span></span>  <br/> |
|<span data-ttu-id="5e46e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5e46e-110">Data type:</span></span>  <br/> |<span data-ttu-id="5e46e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5e46e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5e46e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5e46e-112">Area:</span></span>  <br/> |<span data-ttu-id="5e46e-113">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="5e46e-113">Spam</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5e46e-114">备注</span><span class="sxs-lookup"><span data-stu-id="5e46e-114">Remarks</span></span>

<span data-ttu-id="5e46e-115">如果设置为"0x00000001"，这些电子邮件地址必须填充垃圾邮件规则限制的"受信任的"联系人电子邮件地址部分，这样来自这些地址的邮件将被视为"非垃圾邮件"。</span><span class="sxs-lookup"><span data-stu-id="5e46e-115">If set to "0x00000001", these email addresses must populate the "trusted" contact email address portion of the Junk E-Mail Rule Restriction such that mail from these addresses is treated as "not junk".</span></span> <span data-ttu-id="5e46e-116">如果设置为"0x00000000"，则不得将"联系人"文件夹中的电子邮件地址添加到垃圾邮件规则中，并且该规则部分必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5e46e-116">If set to "0x00000000", email addresses from the Contacts folder must not be added to the Junk E-Mail Rule, and the section of the rule must be NULL.</span></span>
  
<span data-ttu-id="5e46e-117">如果此属性存在值"0x00000001"，并且添加的联系人的电子邮件地址尚未包含在垃圾邮件规则的受信任的联系人部分中，则必须将那些电子邮件地址添加到限制中。</span><span class="sxs-lookup"><span data-stu-id="5e46e-117">If this property is present with a value of "0x00000001" and if the added contact has email addresses that are not yet included in the trusted contacts section of the Junk E-Mail Rule, those email addresses must be added to the restriction.</span></span> <span data-ttu-id="5e46e-118">如果此属性为"0x00000000"，则无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="5e46e-118">If this property is "0x00000000", no action is required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5e46e-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="5e46e-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5e46e-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="5e46e-120">Protocol specifications</span></span>

<span data-ttu-id="5e46e-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e46e-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e46e-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5e46e-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5e46e-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e46e-123">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e46e-124">允许/阻止列表的处理和垃圾邮件的确定。</span><span class="sxs-lookup"><span data-stu-id="5e46e-124">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5e46e-125">头文件</span><span class="sxs-lookup"><span data-stu-id="5e46e-125">Header files</span></span>

<span data-ttu-id="5e46e-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5e46e-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="5e46e-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5e46e-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="5e46e-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5e46e-128">Mapitags.h</span></span>
  
> <span data-ttu-id="5e46e-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5e46e-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5e46e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e46e-130">See also</span></span>



[<span data-ttu-id="5e46e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5e46e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5e46e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e46e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5e46e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5e46e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5e46e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5e46e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

