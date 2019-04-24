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
ms.openlocfilehash: 053ec531f69ff7734872466b7a661beff3177b2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348480"
---
# <a name="pidlidaddressbookprovideremaillist-canonical-property"></a><span data-ttu-id="ab73b-103">PidLidAddressBookProviderEmailList 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab73b-103">PidLidAddressBookProviderEmailList Canonical Property</span></span>

  
  
<span data-ttu-id="ab73b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab73b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab73b-105">指定在联系人上设置的电子地址属性。</span><span class="sxs-lookup"><span data-stu-id="ab73b-105">Specifies which electronic address properties are set on the contact.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ab73b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ab73b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ab73b-107">dispidABPEmailList</span><span class="sxs-lookup"><span data-stu-id="ab73b-107">dispidABPEmailList</span></span>  <br/> |
|<span data-ttu-id="ab73b-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="ab73b-108">Property set:</span></span>  <br/> |<span data-ttu-id="ab73b-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="ab73b-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="ab73b-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="ab73b-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="ab73b-111">0x00008028</span><span class="sxs-lookup"><span data-stu-id="ab73b-111">0x00008028</span></span>  <br/> |
|<span data-ttu-id="ab73b-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ab73b-112">Data type:</span></span>  <br/> |<span data-ttu-id="ab73b-113">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="ab73b-113">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="ab73b-114">区域：</span><span class="sxs-lookup"><span data-stu-id="ab73b-114">Area:</span></span>  <br/> |<span data-ttu-id="ab73b-115">Contact</span><span class="sxs-lookup"><span data-stu-id="ab73b-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ab73b-116">注解</span><span class="sxs-lookup"><span data-stu-id="ab73b-116">Remarks</span></span>

<span data-ttu-id="ab73b-117">此属性中的每个 PT_LONG 值在属性中必须是唯一的, 并且必须设置为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="ab73b-117">Each PT_LONG value in this property must be unique in the property and must be set to one of the values in the following table.</span></span> <span data-ttu-id="ab73b-118">如果设置了此属性, 还必须设置**dispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ab73b-118">If this property is set, the **dispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md)) property must also be set.</span></span> <span data-ttu-id="ab73b-119">这两个属性必须彼此保持同步。</span><span class="sxs-lookup"><span data-stu-id="ab73b-119">These two properties must be kept synchronized with each other.</span></span> <span data-ttu-id="ab73b-120">例如, 如果**dispidABPEmailList**中的某个值为 "0x00000000", 则**dispidABPArrayType**必须设置 "0x00000001" 位。</span><span class="sxs-lookup"><span data-stu-id="ab73b-120">For example, if one of the values in **dispidABPEmailList** is "0x00000000", then **dispidABPArrayType** must have the bit "0x00000001" set.</span></span> 
  
|<span data-ttu-id="ab73b-121">**Value**</span><span class="sxs-lookup"><span data-stu-id="ab73b-121">**Value**</span></span>|<span data-ttu-id="ab73b-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="ab73b-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab73b-123">0x00000000</span><span class="sxs-lookup"><span data-stu-id="ab73b-123">0x00000000</span></span>  <br/> |<span data-ttu-id="ab73b-124">为联系人定义了 "Email1"。</span><span class="sxs-lookup"><span data-stu-id="ab73b-124">Email1 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="ab73b-125">0x00000001</span><span class="sxs-lookup"><span data-stu-id="ab73b-125">0x00000001</span></span>  <br/> |<span data-ttu-id="ab73b-126">为联系人定义了 "Email2"。</span><span class="sxs-lookup"><span data-stu-id="ab73b-126">Email2 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="ab73b-127">0x00000002</span><span class="sxs-lookup"><span data-stu-id="ab73b-127">0x00000002</span></span>  <br/> |<span data-ttu-id="ab73b-128">为联系人定义了 "Email3"。</span><span class="sxs-lookup"><span data-stu-id="ab73b-128">Email3 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="ab73b-129">0x00000003</span><span class="sxs-lookup"><span data-stu-id="ab73b-129">0x00000003</span></span>  <br/> |<span data-ttu-id="ab73b-130">为联系人定义商务传真。</span><span class="sxs-lookup"><span data-stu-id="ab73b-130">Business fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="ab73b-131">0x00000004</span><span class="sxs-lookup"><span data-stu-id="ab73b-131">0x00000004</span></span>  <br/> |<span data-ttu-id="ab73b-132">住宅传真是为联系人定义的。</span><span class="sxs-lookup"><span data-stu-id="ab73b-132">Home fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="ab73b-133">0x00000005</span><span class="sxs-lookup"><span data-stu-id="ab73b-133">0x00000005</span></span>  <br/> |<span data-ttu-id="ab73b-134">为联系人定义了主要传真。</span><span class="sxs-lookup"><span data-stu-id="ab73b-134">Primary fax is defined for the contact.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ab73b-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="ab73b-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ab73b-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="ab73b-136">Protocol specifications</span></span>

<span data-ttu-id="ab73b-137">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab73b-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab73b-138">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ab73b-138">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ab73b-139">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab73b-139">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab73b-140">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ab73b-140">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ab73b-141">头文件</span><span class="sxs-lookup"><span data-stu-id="ab73b-141">Header files</span></span>

<span data-ttu-id="ab73b-142">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ab73b-142">Mapidefs.h</span></span>
  
> <span data-ttu-id="ab73b-143">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ab73b-143">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab73b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab73b-144">See also</span></span>



[<span data-ttu-id="ab73b-145">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ab73b-145">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ab73b-146">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab73b-146">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ab73b-147">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ab73b-147">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ab73b-148">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ab73b-148">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

