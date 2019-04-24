---
title: PidTagAnr 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAnr
api_type:
- HeaderDef
ms.assetid: eca3d4ff-2e92-4d20-a498-98e0773c1962
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ce08ba971662b7f5060e6b24a6d2c5ee1a921d5b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327963"
---
# <a name="pidtaganr-canonical-property"></a><span data-ttu-id="ae43e-103">PidTagAnr 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae43e-103">PidTagAnr Canonical Property</span></span>

  
  
<span data-ttu-id="ae43e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae43e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae43e-105">包含用于在通讯簿容器的内容表上的属性限制中使用的字符串值。</span><span class="sxs-lookup"><span data-stu-id="ae43e-105">Contains a string value for use in a property restriction on an address book container contents table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ae43e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ae43e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ae43e-107">PR_ANR、PR_ANR_A、PR_ANR_W</span><span class="sxs-lookup"><span data-stu-id="ae43e-107">PR_ANR, PR_ANR_A, PR_ANR_W</span></span>  <br/> |
|<span data-ttu-id="ae43e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ae43e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ae43e-109">0x360C</span><span class="sxs-lookup"><span data-stu-id="ae43e-109">0x360C</span></span>  <br/> |
|<span data-ttu-id="ae43e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ae43e-110">Data type:</span></span>  <br/> |<span data-ttu-id="ae43e-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="ae43e-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="ae43e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ae43e-112">Area:</span></span>  <br/> |<span data-ttu-id="ae43e-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="ae43e-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ae43e-114">注解</span><span class="sxs-lookup"><span data-stu-id="ae43e-114">Remarks</span></span>

<span data-ttu-id="ae43e-115">这些属性不属于任何对象;它由[SPropertyRestriction](spropertyrestriction.md)结构中的通讯簿提供程序提供。</span><span class="sxs-lookup"><span data-stu-id="ae43e-115">These properties do not belong to any object; it is furnished by address book providers in [SPropertyRestriction](spropertyrestriction.md) structures.</span></span> <span data-ttu-id="ae43e-116">此属性包含一个不明确的名称解析 (ANR) 字符串, 可以对照通讯簿容器的内容表对其进行测试, 以查找相应的邮件收件人。</span><span class="sxs-lookup"><span data-stu-id="ae43e-116">This property contains an ambiguous name resolution (ANR) string that can be tested against an address book container's contents table to find corresponding message recipients.</span></span> 
  
<span data-ttu-id="ae43e-117">通讯簿提供程序使用提供程序定义的匹配算法, 与内容表中的每个条目的**PR_ANR**和关联属性的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="ae43e-117">Address book providers match the value of **PR_ANR** and associated properties against every entry in the contents table, using a provider-defined matching algorithm.</span></span> <span data-ttu-id="ae43e-118">此匹配中使用的一个或多个列将作为算法的一部分选择提供程序。</span><span class="sxs-lookup"><span data-stu-id="ae43e-118">The column or columns that are used in this match are chosen by the provider as part of the algorithm.</span></span> <span data-ttu-id="ae43e-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列是最常使用的值;**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) 列在包含用户的电子邮件名称时也很有用。</span><span class="sxs-lookup"><span data-stu-id="ae43e-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) column is the most commonly used; the **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) column is also useful when it contains the user's email name.</span></span> 
  
<span data-ttu-id="ae43e-120">有关模糊名称解析的详细信息, 请参阅[通讯簿限制](address-book-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="ae43e-120">For more information on ambiguous name resolution, see [Address Book Restrictions](address-book-restrictions.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ae43e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="ae43e-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ae43e-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="ae43e-122">Protocol specifications</span></span>

<span data-ttu-id="ae43e-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae43e-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae43e-124">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ae43e-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ae43e-125">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae43e-125">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ae43e-126">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ae43e-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ae43e-127">头文件</span><span class="sxs-lookup"><span data-stu-id="ae43e-127">Header files</span></span>

<span data-ttu-id="ae43e-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ae43e-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="ae43e-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ae43e-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="ae43e-130">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ae43e-130">Mapitags.h</span></span>
  
> <span data-ttu-id="ae43e-131">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ae43e-131">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ae43e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae43e-132">See also</span></span>



[<span data-ttu-id="ae43e-133">IAddrBook::ResolveName</span><span class="sxs-lookup"><span data-stu-id="ae43e-133">IAddrBook::ResolveName</span></span>](iaddrbook-resolvename.md)
  
[<span data-ttu-id="ae43e-134">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="ae43e-134">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)


[<span data-ttu-id="ae43e-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ae43e-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ae43e-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ae43e-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ae43e-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ae43e-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ae43e-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ae43e-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

