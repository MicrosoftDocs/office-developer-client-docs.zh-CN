---
title: PidTagGovernmentIdNumber 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagGovernmentIdNumber
api_type:
- HeaderDef
ms.assetid: fa265d37-a1ea-4812-8fe9-21dac374cd7c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4b7ce4620f224597e753fb05ec377461b4c19c9a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316147"
---
# <a name="pidtaggovernmentidnumber-canonical-property"></a><span data-ttu-id="b0e73-103">PidTagGovernmentIdNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0e73-103">PidTagGovernmentIdNumber Canonical Property</span></span>

  
  
<span data-ttu-id="b0e73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0e73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0e73-105">包含收件人政府标识符。</span><span class="sxs-lookup"><span data-stu-id="b0e73-105">Contains a government identifier for the recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b0e73-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b0e73-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b0e73-107">PR_GOVERNMENT_ID_NUMBER、PR_GOVERNMENT_ID_NUMBER_A、PR_GOVERNMENT_ID_NUMBER_W</span><span class="sxs-lookup"><span data-stu-id="b0e73-107">PR_GOVERNMENT_ID_NUMBER, PR_GOVERNMENT_ID_NUMBER_A, PR_GOVERNMENT_ID_NUMBER_W</span></span>  <br/> |
|<span data-ttu-id="b0e73-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b0e73-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b0e73-109">0x3A07</span><span class="sxs-lookup"><span data-stu-id="b0e73-109">0x3A07</span></span>  <br/> |
|<span data-ttu-id="b0e73-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b0e73-110">Data type:</span></span>  <br/> |<span data-ttu-id="b0e73-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b0e73-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b0e73-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b0e73-112">Area:</span></span>  <br/> |<span data-ttu-id="b0e73-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="b0e73-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b0e73-114">备注</span><span class="sxs-lookup"><span data-stu-id="b0e73-114">Remarks</span></span>

<span data-ttu-id="b0e73-115">这些属性提供有关收件人的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="b0e73-115">These properties provide identification and access information about a recipient.</span></span> <span data-ttu-id="b0e73-116">它们由收件人和收件人的组织定义。</span><span class="sxs-lookup"><span data-stu-id="b0e73-116">They are defined by the recipient and the recipient's organization.</span></span> 
  
<span data-ttu-id="b0e73-117">这些属性通常设置为护照号码、公民号码或纳税号码（如社会保险号码）。</span><span class="sxs-lookup"><span data-stu-id="b0e73-117">These properties are commonly set to a passport number, citizen number, or taxpayer number such as a Social Security number.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b0e73-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="b0e73-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b0e73-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="b0e73-119">Protocol specifications</span></span>

<span data-ttu-id="b0e73-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0e73-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0e73-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b0e73-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b0e73-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0e73-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0e73-123">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b0e73-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="b0e73-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b0e73-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b0e73-125">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b0e73-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b0e73-126">头文件</span><span class="sxs-lookup"><span data-stu-id="b0e73-126">Header files</span></span>

<span data-ttu-id="b0e73-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b0e73-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="b0e73-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b0e73-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="b0e73-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b0e73-129">Mapitags.h</span></span>
  
> <span data-ttu-id="b0e73-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b0e73-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b0e73-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e73-131">See also</span></span>



[<span data-ttu-id="b0e73-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b0e73-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b0e73-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0e73-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b0e73-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b0e73-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b0e73-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b0e73-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

