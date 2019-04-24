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
ms.openlocfilehash: 6eafe51490b231b9cc64242595aef54bcc85c3ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360415"
---
# <a name="pidtagassistanttelephonenumber-canonical-property"></a><span data-ttu-id="a53d1-103">PidTagAssistantTelephoneNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="a53d1-103">PidTagAssistantTelephoneNumber Canonical Property</span></span>

  
  
<span data-ttu-id="a53d1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a53d1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a53d1-105">包含收件人的行政助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a53d1-105">Contains the telephone number of the recipient's administrative assistant.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a53d1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a53d1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a53d1-107">PR_ASSISTANT_TELEPHONE_NUMBER、PR_ASSISTANT_TELEPHONE_NUMBER_A、PR_ASSISTANT_TELEPHONE_NUMBER_W</span><span class="sxs-lookup"><span data-stu-id="a53d1-107">PR_ASSISTANT_TELEPHONE_NUMBER, PR_ASSISTANT_TELEPHONE_NUMBER_A, PR_ASSISTANT_TELEPHONE_NUMBER_W</span></span>  <br/> |
|<span data-ttu-id="a53d1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a53d1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a53d1-109">0x3A2E</span><span class="sxs-lookup"><span data-stu-id="a53d1-109">0x3A2E</span></span>  <br/> |
|<span data-ttu-id="a53d1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a53d1-110">Data type:</span></span>  <br/> |<span data-ttu-id="a53d1-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="a53d1-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="a53d1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a53d1-112">Area:</span></span>  <br/> |<span data-ttu-id="a53d1-113">Address</span><span class="sxs-lookup"><span data-stu-id="a53d1-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a53d1-114">注解</span><span class="sxs-lookup"><span data-stu-id="a53d1-114">Remarks</span></span>

<span data-ttu-id="a53d1-115">这些属性可提供收件人的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="a53d1-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="a53d1-116">它们由收件人及其组织定义。</span><span class="sxs-lookup"><span data-stu-id="a53d1-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="a53d1-117">电话号码适用于在**PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md)) 属性中指定的助理。</span><span class="sxs-lookup"><span data-stu-id="a53d1-117">The telephone number is for the assistant specified in the **PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md)) property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a53d1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="a53d1-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a53d1-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="a53d1-119">Protocol specifications</span></span>

<span data-ttu-id="a53d1-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a53d1-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a53d1-121">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="a53d1-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a53d1-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a53d1-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a53d1-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a53d1-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="a53d1-124">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a53d1-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a53d1-125">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a53d1-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a53d1-126">头文件</span><span class="sxs-lookup"><span data-stu-id="a53d1-126">Header files</span></span>

<span data-ttu-id="a53d1-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a53d1-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="a53d1-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a53d1-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="a53d1-129">Mapitags</span><span class="sxs-lookup"><span data-stu-id="a53d1-129">Mapitags.h</span></span>
  
> <span data-ttu-id="a53d1-130">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a53d1-130">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a53d1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a53d1-131">See also</span></span>



[<span data-ttu-id="a53d1-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a53d1-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a53d1-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a53d1-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a53d1-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a53d1-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a53d1-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a53d1-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

