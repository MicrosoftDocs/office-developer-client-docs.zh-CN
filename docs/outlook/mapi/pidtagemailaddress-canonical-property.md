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
ms.openlocfilehash: cb8b7d0fca6b30f75bd35d1e4e48fa359100ad18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777585"
---
# <a name="pidtagemailaddress-canonical-property"></a><span data-ttu-id="3e2bb-103">PidTagEmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="3e2bb-103">PidTagEmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="3e2bb-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e2bb-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e2bb-105">包含消息的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-105">Contains the messaging user's email address.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3e2bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3e2bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3e2bb-107">PR_EMAIL_ADDRESS，PR_EMAIL_ADDRESS_A，PR_EMAIL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="3e2bb-107">PR_EMAIL_ADDRESS, PR_EMAIL_ADDRESS_A, PR_EMAIL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="3e2bb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3e2bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3e2bb-109">0x3003</span><span class="sxs-lookup"><span data-stu-id="3e2bb-109">0x3003</span></span>  <br/> |
|<span data-ttu-id="3e2bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3e2bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="3e2bb-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3e2bb-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3e2bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3e2bb-112">Area:</span></span>  <br/> |<span data-ttu-id="3e2bb-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="3e2bb-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3e2bb-114">说明</span><span class="sxs-lookup"><span data-stu-id="3e2bb-114">Remarks</span></span>

<span data-ttu-id="3e2bb-115">这些属性是所有邮件用户的基址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-115">These properties are examples of the base address properties for all messaging users.</span></span> <span data-ttu-id="3e2bb-116">它是以 null 结尾的字符串，其格式有意义仅为基础邮件系统。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-116">It is a null-terminated string whose format has meaning only for the underlying messaging system.</span></span> 
  
<span data-ttu-id="3e2bb-117">与**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 和**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 寻址的消息中的属性结合使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-117">These properties are used in conjunction with the **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) and **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) properties in addressing messages.</span></span> <span data-ttu-id="3e2bb-118">字符串格式是由**PR_ADDRTYPE**限定。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-118">The string format is qualified by **PR_ADDRTYPE**.</span></span> 
  
<span data-ttu-id="3e2bb-119">此属性的有效值包括：</span><span class="sxs-lookup"><span data-stu-id="3e2bb-119">Valid values for this property include:</span></span> 
  
```cpp
network/postoffice/user 
Bruce@XYZZY.COM 
/c=US/a=att/p=Microsoft/o=Finance/ou=Purchasing/s=Furthur/g=Joe 
 
```

## <a name="related-resources"></a><span data-ttu-id="3e2bb-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="3e2bb-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3e2bb-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="3e2bb-121">Protocol specifications</span></span>

<span data-ttu-id="3e2bb-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e2bb-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3e2bb-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3e2bb-124">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e2bb-124">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3e2bb-125">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="3e2bb-126">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e2bb-126">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3e2bb-127">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-127">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3e2bb-128">头文件</span><span class="sxs-lookup"><span data-stu-id="3e2bb-128">Header files</span></span>

<span data-ttu-id="3e2bb-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3e2bb-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="3e2bb-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="3e2bb-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3e2bb-131">Mapitags.h</span></span>
  
> <span data-ttu-id="3e2bb-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3e2bb-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3e2bb-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e2bb-133">See also</span></span>



[<span data-ttu-id="3e2bb-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3e2bb-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3e2bb-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3e2bb-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3e2bb-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3e2bb-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3e2bb-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3e2bb-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

