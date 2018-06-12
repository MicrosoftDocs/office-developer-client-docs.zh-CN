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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b2ac7aa4fca8583fc59d727c55433108bee62dee
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777677"
---
# <a name="pidtaggender-canonical-property"></a><span data-ttu-id="1c6a0-103">PidTagGender 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6a0-103">PidTagGender Canonical Property</span></span>

  
  
<span data-ttu-id="1c6a0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1c6a0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1c6a0-105">包含消息的用户的性别。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-105">Contains the gender of the messaging user.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1c6a0-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="1c6a0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1c6a0-107">PR_GENDER</span><span class="sxs-lookup"><span data-stu-id="1c6a0-107">PR_GENDER</span></span>  <br/> |
|<span data-ttu-id="1c6a0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1c6a0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1c6a0-109">0x3A4D</span><span class="sxs-lookup"><span data-stu-id="1c6a0-109">0x3A4D</span></span>  <br/> |
|<span data-ttu-id="1c6a0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1c6a0-110">Data type:</span></span>  <br/> |<span data-ttu-id="1c6a0-111">PT_I2</span><span class="sxs-lookup"><span data-stu-id="1c6a0-111">PT_I2</span></span>  <br/> |
|<span data-ttu-id="1c6a0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1c6a0-112">Area:</span></span>  <br/> |<span data-ttu-id="1c6a0-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="1c6a0-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1c6a0-114">备注</span><span class="sxs-lookup"><span data-stu-id="1c6a0-114">Remarks</span></span>

<span data-ttu-id="1c6a0-115">此属性提供标识和访问有关消息的用户信息并且其内容。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-115">This property provides identification and access information about a messaging user and the content is.</span></span> <span data-ttu-id="1c6a0-116">按消息的用户和邮件用户的组织定义的内容。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-116">The content is defined by the messaging user and the messaging user's organization.</span></span> 
  
<span data-ttu-id="1c6a0-117">此属性的可能值是性别枚举中定义的。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-117">The possible values for this property are defined in the gender enumeration.</span></span> <span data-ttu-id="1c6a0-118">排列，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c6a0-118">They are listed as follows:</span></span>
  
|<span data-ttu-id="1c6a0-119">**性别枚举**</span><span class="sxs-lookup"><span data-stu-id="1c6a0-119">**Gender enumeration**</span></span>|<span data-ttu-id="1c6a0-120">**值**</span><span class="sxs-lookup"><span data-stu-id="1c6a0-120">**Value**</span></span>|<span data-ttu-id="1c6a0-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="1c6a0-121">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c6a0-122">genderUnspecified</span><span class="sxs-lookup"><span data-stu-id="1c6a0-122">genderUnspecified</span></span>  <br/> |<span data-ttu-id="1c6a0-123">0x0000</span><span class="sxs-lookup"><span data-stu-id="1c6a0-123">0x0000</span></span>  <br/> |<span data-ttu-id="1c6a0-124">未指定联系人的性别。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-124">The contact's gender is unspecified.</span></span>  <br/> |
|<span data-ttu-id="1c6a0-125">genderFemale</span><span class="sxs-lookup"><span data-stu-id="1c6a0-125">genderFemale</span></span>  <br/> |<span data-ttu-id="1c6a0-126">0x0001</span><span class="sxs-lookup"><span data-stu-id="1c6a0-126">0x0001</span></span>  <br/> |<span data-ttu-id="1c6a0-127">联系人正在女。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-127">The contact is female.</span></span>  <br/> |
|<span data-ttu-id="1c6a0-128">genderMale</span><span class="sxs-lookup"><span data-stu-id="1c6a0-128">genderMale</span></span>  <br/> |<span data-ttu-id="1c6a0-129">0x0002</span><span class="sxs-lookup"><span data-stu-id="1c6a0-129">0x0002</span></span>  <br/> |<span data-ttu-id="1c6a0-130">联系人正在男性。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-130">The contact is male.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1c6a0-131">相关资源</span><span class="sxs-lookup"><span data-stu-id="1c6a0-131">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1c6a0-132">协议规范</span><span class="sxs-lookup"><span data-stu-id="1c6a0-132">Protocol specifications</span></span>

<span data-ttu-id="1c6a0-133">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1c6a0-133">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1c6a0-134">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-134">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1c6a0-135">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1c6a0-135">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1c6a0-136">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-136">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="1c6a0-137">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1c6a0-137">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1c6a0-138">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-138">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1c6a0-139">头文件</span><span class="sxs-lookup"><span data-stu-id="1c6a0-139">Header files</span></span>

<span data-ttu-id="1c6a0-140">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1c6a0-140">Mapidefs.h</span></span>
  
> <span data-ttu-id="1c6a0-141">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-141">Provides data type definitions.</span></span>
    
<span data-ttu-id="1c6a0-142">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1c6a0-142">Mapitags.h</span></span>
  
> <span data-ttu-id="1c6a0-143">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1c6a0-143">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1c6a0-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c6a0-144">See also</span></span>



[<span data-ttu-id="1c6a0-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1c6a0-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1c6a0-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6a0-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1c6a0-147">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1c6a0-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1c6a0-148">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1c6a0-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

