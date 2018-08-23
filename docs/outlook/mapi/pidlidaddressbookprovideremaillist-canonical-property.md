---
title: PidLidAddressBookProviderEmailList 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderEmailList
api_type:
- COM
ms.assetid: 9c0527ea-e922-4514-b913-d3520350c452
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9f73720860aa0ec54289f25a553bb00bfbe76b6a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581046"
---
# <a name="pidlidaddressbookprovideremaillist-canonical-property"></a><span data-ttu-id="28006-103">PidLidAddressBookProviderEmailList 规范属性</span><span class="sxs-lookup"><span data-stu-id="28006-103">PidLidAddressBookProviderEmailList Canonical Property</span></span>

  
  
<span data-ttu-id="28006-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28006-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28006-105">指定哪个电子通讯属性设置该联系人上。</span><span class="sxs-lookup"><span data-stu-id="28006-105">Specifies which electronic address properties are set on the contact.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="28006-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="28006-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="28006-107">dispidABPEmailList</span><span class="sxs-lookup"><span data-stu-id="28006-107">dispidABPEmailList</span></span>  <br/> |
|<span data-ttu-id="28006-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="28006-108">Property set:</span></span>  <br/> |<span data-ttu-id="28006-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="28006-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="28006-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="28006-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="28006-111">0x00008028</span><span class="sxs-lookup"><span data-stu-id="28006-111">0x00008028</span></span>  <br/> |
|<span data-ttu-id="28006-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="28006-112">Data type:</span></span>  <br/> |<span data-ttu-id="28006-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="28006-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="28006-114">区域：</span><span class="sxs-lookup"><span data-stu-id="28006-114">Area:</span></span>  <br/> |<span data-ttu-id="28006-115">联系人</span><span class="sxs-lookup"><span data-stu-id="28006-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="28006-116">注解</span><span class="sxs-lookup"><span data-stu-id="28006-116">Remarks</span></span>

<span data-ttu-id="28006-117">此属性中的每个 PT_LONG 值必须是唯一的属性中，并且必须设置为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="28006-117">Each PT_LONG value in this property must be unique in the property and must be set to one of the values in the following table.</span></span> <span data-ttu-id="28006-118">如果设置此属性，还必须设置**dispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="28006-118">If this property is set, the **dispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md)) property must also be set.</span></span> <span data-ttu-id="28006-119">这两个属性必须保持相互同步。</span><span class="sxs-lookup"><span data-stu-id="28006-119">These two properties must be kept synchronized with each other.</span></span> <span data-ttu-id="28006-120">例如，如果一个**dispidABPEmailList**中的值是"0x00000000"，然后**dispidABPArrayType**必须具有位"0x00000001"设置。</span><span class="sxs-lookup"><span data-stu-id="28006-120">For example, if one of the values in **dispidABPEmailList** is "0x00000000", then **dispidABPArrayType** must have the bit "0x00000001" set.</span></span> 
  
|<span data-ttu-id="28006-121">**值**</span><span class="sxs-lookup"><span data-stu-id="28006-121">**Value**</span></span>|<span data-ttu-id="28006-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="28006-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28006-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="28006-123">0x00000000</span></span>  <br/> |<span data-ttu-id="28006-124">为该联系人定义电子邮件 1。</span><span class="sxs-lookup"><span data-stu-id="28006-124">Email1 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="28006-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="28006-125">0x00000001</span></span>  <br/> |<span data-ttu-id="28006-126">为该联系人定义电子邮件 2。</span><span class="sxs-lookup"><span data-stu-id="28006-126">Email2 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="28006-127">0x00000002</span><span class="sxs-lookup"><span data-stu-id="28006-127">0x00000002</span></span>  <br/> |<span data-ttu-id="28006-128">为该联系人定义电子邮件 3。</span><span class="sxs-lookup"><span data-stu-id="28006-128">Email3 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="28006-129">0x00000003</span><span class="sxs-lookup"><span data-stu-id="28006-129">0x00000003</span></span>  <br/> |<span data-ttu-id="28006-130">商务传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="28006-130">Business fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="28006-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="28006-131">0x00000004</span></span>  <br/> |<span data-ttu-id="28006-132">住宅传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="28006-132">Home fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="28006-133">0x00000005</span><span class="sxs-lookup"><span data-stu-id="28006-133">0x00000005</span></span>  <br/> |<span data-ttu-id="28006-134">主要传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="28006-134">Primary fax is defined for the contact.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="28006-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="28006-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="28006-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="28006-136">Protocol specifications</span></span>

<span data-ttu-id="28006-137">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="28006-137">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="28006-138">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="28006-138">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="28006-139">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="28006-139">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="28006-140">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="28006-140">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="28006-141">头文件</span><span class="sxs-lookup"><span data-stu-id="28006-141">Header files</span></span>

<span data-ttu-id="28006-142">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="28006-142">Mapidefs.h</span></span>
  
> <span data-ttu-id="28006-143">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="28006-143">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="28006-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28006-144">See also</span></span>



[<span data-ttu-id="28006-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="28006-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="28006-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="28006-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="28006-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="28006-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="28006-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="28006-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

