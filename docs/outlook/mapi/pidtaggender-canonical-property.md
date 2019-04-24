---
title: PidTagGender 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagGender
api_type:
- HeaderDef
ms.assetid: a79a139a-6813-49f6-b622-bb66d62c4462
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b8ce3898ac021bc6eec2af6220889d71ff5a18dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316154"
---
# <a name="pidtaggender-canonical-property"></a><span data-ttu-id="befa7-103">PidTagGender 规范属性</span><span class="sxs-lookup"><span data-stu-id="befa7-103">PidTagGender Canonical Property</span></span>

  
  
<span data-ttu-id="befa7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="befa7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="befa7-105">包含邮件用户的性别。</span><span class="sxs-lookup"><span data-stu-id="befa7-105">Contains the gender of the messaging user.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="befa7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="befa7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="befa7-107">PR_GENDER</span><span class="sxs-lookup"><span data-stu-id="befa7-107">PR_GENDER</span></span>  <br/> |
|<span data-ttu-id="befa7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="befa7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="befa7-109">0x3A4D</span><span class="sxs-lookup"><span data-stu-id="befa7-109">0x3A4D</span></span>  <br/> |
|<span data-ttu-id="befa7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="befa7-110">Data type:</span></span>  <br/> |<span data-ttu-id="befa7-111">PT_I2</span><span class="sxs-lookup"><span data-stu-id="befa7-111">PT_I2</span></span>  <br/> |
|<span data-ttu-id="befa7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="befa7-112">Area:</span></span>  <br/> |<span data-ttu-id="befa7-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="befa7-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="befa7-114">注解</span><span class="sxs-lookup"><span data-stu-id="befa7-114">Remarks</span></span>

<span data-ttu-id="befa7-115">此属性提供有关邮件用户和内容的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="befa7-115">This property provides identification and access information about a messaging user and the content is.</span></span> <span data-ttu-id="befa7-116">内容由邮件用户和邮件用户的组织定义。</span><span class="sxs-lookup"><span data-stu-id="befa7-116">The content is defined by the messaging user and the messaging user's organization.</span></span> 
  
<span data-ttu-id="befa7-117">此属性的可能值是在性别枚举中定义的。</span><span class="sxs-lookup"><span data-stu-id="befa7-117">The possible values for this property are defined in the gender enumeration.</span></span> <span data-ttu-id="befa7-118">它们按如下方式列出:</span><span class="sxs-lookup"><span data-stu-id="befa7-118">They are listed as follows:</span></span>
  
|<span data-ttu-id="befa7-119">**性别枚举**</span><span class="sxs-lookup"><span data-stu-id="befa7-119">**Gender enumeration**</span></span>|<span data-ttu-id="befa7-120">**Value**</span><span class="sxs-lookup"><span data-stu-id="befa7-120">**Value**</span></span>|<span data-ttu-id="befa7-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="befa7-121">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="befa7-122">genderUnspecified</span><span class="sxs-lookup"><span data-stu-id="befa7-122">genderUnspecified</span></span>  <br/> |<span data-ttu-id="befa7-123">0x0000</span><span class="sxs-lookup"><span data-stu-id="befa7-123">0x0000</span></span>  <br/> |<span data-ttu-id="befa7-124">未指定联系人的性别。</span><span class="sxs-lookup"><span data-stu-id="befa7-124">The contact's gender is unspecified.</span></span>  <br/> |
|<span data-ttu-id="befa7-125">genderFemale</span><span class="sxs-lookup"><span data-stu-id="befa7-125">genderFemale</span></span>  <br/> |<span data-ttu-id="befa7-126">0x0001</span><span class="sxs-lookup"><span data-stu-id="befa7-126">0x0001</span></span>  <br/> |<span data-ttu-id="befa7-127">联系人为 "女"。</span><span class="sxs-lookup"><span data-stu-id="befa7-127">The contact is female.</span></span>  <br/> |
|<span data-ttu-id="befa7-128">genderMale</span><span class="sxs-lookup"><span data-stu-id="befa7-128">genderMale</span></span>  <br/> |<span data-ttu-id="befa7-129">0x0002</span><span class="sxs-lookup"><span data-stu-id="befa7-129">0x0002</span></span>  <br/> |<span data-ttu-id="befa7-130">联系人是男。</span><span class="sxs-lookup"><span data-stu-id="befa7-130">The contact is male.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="befa7-131">相关资源</span><span class="sxs-lookup"><span data-stu-id="befa7-131">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="befa7-132">协议规范</span><span class="sxs-lookup"><span data-stu-id="befa7-132">Protocol specifications</span></span>

<span data-ttu-id="befa7-133">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="befa7-133">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="befa7-134">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="befa7-134">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="befa7-135">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="befa7-135">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="befa7-136">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="befa7-136">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="befa7-137">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="befa7-137">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="befa7-138">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="befa7-138">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="befa7-139">头文件</span><span class="sxs-lookup"><span data-stu-id="befa7-139">Header files</span></span>

<span data-ttu-id="befa7-140">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="befa7-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="befa7-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="befa7-141">Provides data type definitions.</span></span>
    
<span data-ttu-id="befa7-142">Mapitags</span><span class="sxs-lookup"><span data-stu-id="befa7-142">Mapitags.h</span></span>
  
> <span data-ttu-id="befa7-143">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="befa7-143">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="befa7-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="befa7-144">See also</span></span>



[<span data-ttu-id="befa7-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="befa7-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="befa7-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="befa7-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="befa7-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="befa7-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="befa7-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="befa7-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

