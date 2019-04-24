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
ms.openlocfilehash: 68396f210aab465da9cec4a74a3c24cc4e8578a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348438"
---
# <a name="pidlidaddressbookproviderarraytype-canonical-property"></a><span data-ttu-id="728c4-103">PidLidAddressBookProviderArrayType 规范属性</span><span class="sxs-lookup"><span data-stu-id="728c4-103">PidLidAddressBookProviderArrayType Canonical Property</span></span>

  
  
<span data-ttu-id="728c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="728c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="728c4-105">指定联系人电子地址的状态并代表一组位标志。</span><span class="sxs-lookup"><span data-stu-id="728c4-105">Specifies the state of the contact's electronic addresses and represents a set of bit flags.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="728c4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="728c4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="728c4-107">dispidABPArrayType</span><span class="sxs-lookup"><span data-stu-id="728c4-107">dispidABPArrayType</span></span>  <br/> |
|<span data-ttu-id="728c4-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="728c4-108">Property set:</span></span>  <br/> |<span data-ttu-id="728c4-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="728c4-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="728c4-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="728c4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="728c4-111">0x00008029</span><span class="sxs-lookup"><span data-stu-id="728c4-111">0x00008029</span></span>  <br/> |
|<span data-ttu-id="728c4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="728c4-112">Data type:</span></span>  <br/> |<span data-ttu-id="728c4-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="728c4-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="728c4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="728c4-114">Area:</span></span>  <br/> |<span data-ttu-id="728c4-115">Contact</span><span class="sxs-lookup"><span data-stu-id="728c4-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="728c4-116">注解</span><span class="sxs-lookup"><span data-stu-id="728c4-116">Remarks</span></span>

<span data-ttu-id="728c4-117">**dispidABPArrayType**属性的值必须是指定 contact 对象的状态的标志的组合。</span><span class="sxs-lookup"><span data-stu-id="728c4-117">The value of the **dispidABPArrayType** property must be a combination of flags that specify the state of the contact object.</span></span> <span data-ttu-id="728c4-118">下表中指定了各个标志。</span><span class="sxs-lookup"><span data-stu-id="728c4-118">Individual flags are specified in the following table.</span></span> <span data-ttu-id="728c4-119">如果设置了此属性, 则还必须设置**dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="728c4-119">If this property is set, the **dispidABPEmailList** ([PidLidAddressBookProviderEmailList](pidlidaddressbookprovideremaillist-canonical-property.md)) property must be set, as well.</span></span> <span data-ttu-id="728c4-120">这两个属性必须彼此保持同步。</span><span class="sxs-lookup"><span data-stu-id="728c4-120">These two properties must be kept synchronized with each other.</span></span> <span data-ttu-id="728c4-121">例如, 如果**dispidABPArrayType**具有位 "0x00000001 set", 则**dispidABPEmailList**的值之一必须为 "0x00000000"。</span><span class="sxs-lookup"><span data-stu-id="728c4-121">For example, if **dispidABPArrayType** has the bit "0x00000001 set", one of the values of **dispidABPEmailList** must be "0x00000000".</span></span> 
  
|<span data-ttu-id="728c4-122">**位**</span><span class="sxs-lookup"><span data-stu-id="728c4-122">**Bit**</span></span>|<span data-ttu-id="728c4-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="728c4-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="728c4-124">0x00000001</span><span class="sxs-lookup"><span data-stu-id="728c4-124">0x00000001</span></span>  <br/> |<span data-ttu-id="728c4-125">为联系人定义了 "Email1"。</span><span class="sxs-lookup"><span data-stu-id="728c4-125">Email1 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="728c4-126">0x00000002</span><span class="sxs-lookup"><span data-stu-id="728c4-126">0x00000002</span></span>  <br/> |<span data-ttu-id="728c4-127">为联系人定义了 "Email2"。</span><span class="sxs-lookup"><span data-stu-id="728c4-127">Email2 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="728c4-128">0x00000004</span><span class="sxs-lookup"><span data-stu-id="728c4-128">0x00000004</span></span>  <br/> |<span data-ttu-id="728c4-129">为联系人定义了 "Email3"。</span><span class="sxs-lookup"><span data-stu-id="728c4-129">Email3 is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="728c4-130">0x00000008</span><span class="sxs-lookup"><span data-stu-id="728c4-130">0x00000008</span></span>  <br/> |<span data-ttu-id="728c4-131">为联系人定义商务传真。</span><span class="sxs-lookup"><span data-stu-id="728c4-131">Business fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="728c4-132">0x00000010</span><span class="sxs-lookup"><span data-stu-id="728c4-132">0x00000010</span></span>  <br/> |<span data-ttu-id="728c4-133">住宅传真是为联系人定义的。</span><span class="sxs-lookup"><span data-stu-id="728c4-133">Home fax is defined for the contact.</span></span>  <br/> |
|<span data-ttu-id="728c4-134">0x00000020</span><span class="sxs-lookup"><span data-stu-id="728c4-134">0x00000020</span></span>  <br/> |<span data-ttu-id="728c4-135">为联系人定义了主要传真。</span><span class="sxs-lookup"><span data-stu-id="728c4-135">Primary fax is defined for the contact.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="728c4-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="728c4-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="728c4-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="728c4-137">Protocol specifications</span></span>

<span data-ttu-id="728c4-138">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="728c4-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="728c4-139">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="728c4-139">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="728c4-140">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="728c4-140">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="728c4-141">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="728c4-141">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="728c4-142">头文件</span><span class="sxs-lookup"><span data-stu-id="728c4-142">Header files</span></span>

<span data-ttu-id="728c4-143">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="728c4-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="728c4-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="728c4-144">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="728c4-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="728c4-145">See also</span></span>



[<span data-ttu-id="728c4-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="728c4-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="728c4-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="728c4-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="728c4-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="728c4-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="728c4-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="728c4-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

