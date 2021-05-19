---
title: PidTagEmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEmailAddress
api_type:
- HeaderDef
ms.assetid: bbd1e187-172e-4612-9efe-7c8e52967dfe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efcb72d872836adce544f3a90cf093de1f3713a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338638"
---
# <a name="pidtagemailaddress-canonical-property"></a><span data-ttu-id="34379-103">PidTagEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="34379-103">PidTagEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="34379-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34379-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34379-105">包含邮件用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="34379-105">Contains the messaging user's email address.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="34379-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="34379-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="34379-107">PR_EMAIL_ADDRESS、PR_EMAIL_ADDRESS_A、PR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="34379-107">PR_EMAIL_ADDRESS, PR_EMAIL_ADDRESS_A, PR_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="34379-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="34379-108">Identifier:</span></span>  <br/> |<span data-ttu-id="34379-109">0x3003</span><span class="sxs-lookup"><span data-stu-id="34379-109">0x3003</span></span>  <br/> |
|<span data-ttu-id="34379-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="34379-110">Data type:</span></span>  <br/> |<span data-ttu-id="34379-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="34379-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="34379-112">区域：</span><span class="sxs-lookup"><span data-stu-id="34379-112">Area:</span></span>  <br/> |<span data-ttu-id="34379-113">MAPI common</span><span class="sxs-lookup"><span data-stu-id="34379-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34379-114">备注</span><span class="sxs-lookup"><span data-stu-id="34379-114">Remarks</span></span>

<span data-ttu-id="34379-115">这些属性是所有邮件用户的基本地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="34379-115">These properties are examples of the base address properties for all messaging users.</span></span> <span data-ttu-id="34379-116">它是一个以 null 结尾的字符串，其格式仅对基础邮件系统有意义。</span><span class="sxs-lookup"><span data-stu-id="34379-116">It is a null-terminated string whose format has meaning only for the underlying messaging system.</span></span> 
  
<span data-ttu-id="34379-117">这些属性与 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和 **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性一起使用来寻址邮件。</span><span class="sxs-lookup"><span data-stu-id="34379-117">These properties are used in conjunction with the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) and **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) properties in addressing messages.</span></span> <span data-ttu-id="34379-118">字符串格式由 **PR_ADDRTYPE** 限定。</span><span class="sxs-lookup"><span data-stu-id="34379-118">The string format is qualified by **PR_ADDRTYPE**.</span></span> 
  
<span data-ttu-id="34379-119">此属性的有效值包括：</span><span class="sxs-lookup"><span data-stu-id="34379-119">Valid values for this property include:</span></span> 
  
```cpp
network/postoffice/user 
Bruce@XYZZY.COM 
/c=US/a=att/p=Microsoft/o=Finance/ou=Purchasing/s=Furthur/g=Joe 
 
```

## <a name="related-resources"></a><span data-ttu-id="34379-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="34379-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="34379-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="34379-121">Protocol specifications</span></span>

<span data-ttu-id="34379-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34379-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34379-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="34379-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="34379-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34379-124">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34379-125">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="34379-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="34379-126">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34379-126">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34379-127">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="34379-127">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="34379-128">头文件</span><span class="sxs-lookup"><span data-stu-id="34379-128">Header files</span></span>

<span data-ttu-id="34379-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="34379-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="34379-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="34379-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="34379-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="34379-131">Mapitags.h</span></span>
  
> <span data-ttu-id="34379-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="34379-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34379-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34379-133">See also</span></span>



[<span data-ttu-id="34379-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="34379-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="34379-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="34379-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="34379-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="34379-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="34379-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="34379-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

