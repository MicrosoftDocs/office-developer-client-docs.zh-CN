---
title: PidLidAddressBookProviderArrayType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderArrayType
api_type:
- COM
ms.assetid: ca4eb6c2-98e9-4dbc-9f5a-f0f257456ead
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3515d0f751cb6d8d0d427079691456519bac97dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776578"
---
# <a name="pidlidaddressbookproviderarraytype-canonical-property"></a><span data-ttu-id="6b290-103">PidLidAddressBookProviderArrayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b290-103">PidLidAddressBookProviderArrayType Canonical Property</span></span>

  
  
<span data-ttu-id="6b290-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6b290-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6b290-105">指定联系人的电子地址的状态，表示一位标志。</span><span class="sxs-lookup"><span data-stu-id="6b290-105">Specifies the state of the contact's electronic addresses and represents a set of bit flags.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6b290-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6b290-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6b290-107">dispidABPArrayType</span><span class="sxs-lookup"><span data-stu-id="6b290-107">dispidABPArrayType</span></span>  <br/> |
|<span data-ttu-id="6b290-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6b290-108">Property set:</span></span>  <br/> |<span data-ttu-id="6b290-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="6b290-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="6b290-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6b290-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6b290-111">0x00008029</span><span class="sxs-lookup"><span data-stu-id="6b290-111">0x00008029</span></span>  <br/> |
|<span data-ttu-id="6b290-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6b290-112">Data type:</span></span>  <br/> |<span data-ttu-id="6b290-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6b290-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6b290-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6b290-114">Area:</span></span>  <br/> |<span data-ttu-id="6b290-115">联系人</span><span class="sxs-lookup"><span data-stu-id="6b290-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6b290-116">说明</span><span class="sxs-lookup"><span data-stu-id="6b290-116">Remarks</span></span>

<span data-ttu-id="6b290-117">**DispidABPArrayType**属性的值必须是指定联系对象的状态标志的组合。</span><span class="sxs-lookup"><span data-stu-id="6b290-117">The value of the **dispidABPArrayType** property must be a combination of flags that specify the state of the contact object.</span></span> <span data-ttu-id="6b290-118">下表中指定的单个标志。</span><span class="sxs-lookup"><span data-stu-id="6b290-118">Individual flags are specified in the following table.</span></span> <span data-ttu-id="6b290-119">如果设置此属性， **dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) 属性必须设置，以及。</span><span class="sxs-lookup"><span data-stu-id="6b290-119">If this property is set, the **dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) property must be set, as well.</span></span> <span data-ttu-id="6b290-120">这两个属性必须保持相互同步。</span><span class="sxs-lookup"><span data-stu-id="6b290-120">These two properties must be kept synchronized with each other.</span></span> <span data-ttu-id="6b290-121">例如，如果**dispidABPArrayType**位"0x00000001 设置"， **dispidABPEmailList**值之一必须是"0x00000000"。</span><span class="sxs-lookup"><span data-stu-id="6b290-121">For example, if **dispidABPArrayType** has the bit "0x00000001 set", one of the values of **dispidABPEmailList** must be "0x00000000".</span></span> 
  
|<span data-ttu-id="6b290-122">**位**</span><span class="sxs-lookup"><span data-stu-id="6b290-122">**Bit**</span></span>|<span data-ttu-id="6b290-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b290-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b290-124">0x00000001</span><span class="sxs-lookup"><span data-stu-id="6b290-124">0x00000001</span></span>  <br/> |<span data-ttu-id="6b290-125">为该联系人定义电子邮件 1。</span><span class="sxs-lookup"><span data-stu-id="6b290-125">Email1 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="6b290-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="6b290-126">0x00000002</span></span>  <br/> |<span data-ttu-id="6b290-127">为该联系人定义电子邮件 2。</span><span class="sxs-lookup"><span data-stu-id="6b290-127">Email2 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="6b290-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="6b290-128">0x00000004</span></span>  <br/> |<span data-ttu-id="6b290-129">为该联系人定义电子邮件 3。</span><span class="sxs-lookup"><span data-stu-id="6b290-129">Email3 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="6b290-130">0x00000008</span><span class="sxs-lookup"><span data-stu-id="6b290-130">0x00000008</span></span>  <br/> |<span data-ttu-id="6b290-131">商务传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="6b290-131">Business fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="6b290-132">0x00000010</span><span class="sxs-lookup"><span data-stu-id="6b290-132">0x00000010</span></span>  <br/> |<span data-ttu-id="6b290-133">住宅传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="6b290-133">Home fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="6b290-134">0x00000020</span><span class="sxs-lookup"><span data-stu-id="6b290-134">0x00000020</span></span>  <br/> |<span data-ttu-id="6b290-135">主要传真定义为该联系人。</span><span class="sxs-lookup"><span data-stu-id="6b290-135">Primary fax is defined for the contact.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="6b290-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="6b290-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6b290-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="6b290-137">Protocol specifications</span></span>

<span data-ttu-id="6b290-138">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6b290-138">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6b290-139">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6b290-139">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6b290-140">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6b290-140">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6b290-141">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="6b290-141">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6b290-142">头文件</span><span class="sxs-lookup"><span data-stu-id="6b290-142">Header files</span></span>

<span data-ttu-id="6b290-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6b290-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="6b290-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6b290-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6b290-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b290-145">See also</span></span>



[<span data-ttu-id="6b290-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6b290-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6b290-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6b290-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6b290-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6b290-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6b290-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6b290-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

