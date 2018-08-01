---
title: PidTagAssistantTelephoneNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAssistantTelephoneNumber
api_type:
- HeaderDef
ms.assetid: edb0782c-6671-4e98-9028-a2f9ad547c1d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1242415e0698acb210f3e9ef8bfa00fd944816d3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777330"
---
# <a name="pidtagassistanttelephonenumber-canonical-property"></a><span data-ttu-id="f6334-103">PidTagAssistantTelephoneNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6334-103">PidTagAssistantTelephoneNumber Canonical Property</span></span>

  
  
<span data-ttu-id="f6334-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f6334-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f6334-105">包含收信人行政助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f6334-105">Contains the telephone number of the recipient's administrative assistant.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f6334-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f6334-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f6334-107">PR_ASSISTANT_TELEPHONE_NUMBER，PR_ASSISTANT_TELEPHONE_NUMBER_A，PR_ASSISTANT_TELEPHONE_NUMBER_W</span><span class="sxs-lookup"><span data-stu-id="f6334-107">PR_ASSISTANT_TELEPHONE_NUMBER, PR_ASSISTANT_TELEPHONE_NUMBER_A, PR_ASSISTANT_TELEPHONE_NUMBER_W</span></span>  <br/> |
|<span data-ttu-id="f6334-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f6334-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f6334-109">0x3A2E</span><span class="sxs-lookup"><span data-stu-id="f6334-109">0x3A2E</span></span>  <br/> |
|<span data-ttu-id="f6334-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f6334-110">Data type:</span></span>  <br/> |<span data-ttu-id="f6334-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="f6334-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="f6334-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f6334-112">Area:</span></span>  <br/> |<span data-ttu-id="f6334-113">Address</span><span class="sxs-lookup"><span data-stu-id="f6334-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f6334-114">说明</span><span class="sxs-lookup"><span data-stu-id="f6334-114">Remarks</span></span>

<span data-ttu-id="f6334-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="f6334-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="f6334-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="f6334-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="f6334-117">助理**PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md)) 属性中指定的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f6334-117">The telephone number is for the assistant specified in the **PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md)) property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f6334-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f6334-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f6334-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f6334-119">Protocol specifications</span></span>

<span data-ttu-id="f6334-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6334-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f6334-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="f6334-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f6334-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6334-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f6334-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="f6334-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="f6334-124">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6334-124">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f6334-125">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="f6334-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f6334-126">头文件</span><span class="sxs-lookup"><span data-stu-id="f6334-126">Header files</span></span>

<span data-ttu-id="f6334-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f6334-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="f6334-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f6334-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="f6334-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f6334-129">Mapitags.h</span></span>
  
> <span data-ttu-id="f6334-130">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f6334-130">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f6334-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6334-131">See also</span></span>



[<span data-ttu-id="f6334-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f6334-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f6334-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6334-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f6334-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f6334-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f6334-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f6334-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

