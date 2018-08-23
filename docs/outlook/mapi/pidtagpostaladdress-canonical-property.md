---
title: PidTagPostalAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagPostalAddress
api_type:
- COM
ms.assetid: cf400713-3b42-4ee7-9dea-d52b8bf03ac3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5456cedb8882bc43b7ee59b53ffb7d6ba40c3414
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569027"
---
# <a name="pidtagpostaladdress-canonical-property"></a><span data-ttu-id="5c6a3-103">PidTagPostalAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="5c6a3-103">PidTagPostalAddress Canonical Property</span></span>

  
  
<span data-ttu-id="5c6a3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5c6a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5c6a3-105">包含收信人的邮政地址。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-105">Contains the recipient's postal address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5c6a3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5c6a3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5c6a3-107">PR_POSTAL_ADDRESS，PR_POSTAL_ADDRESS_A，PR_POSTAL_ADDRESS_W</span><span class="sxs-lookup"><span data-stu-id="5c6a3-107">PR_POSTAL_ADDRESS, PR_POSTAL_ADDRESS_A, PR_POSTAL_ADDRESS_W</span></span>  <br/> |
|<span data-ttu-id="5c6a3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5c6a3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5c6a3-109">0x3A15</span><span class="sxs-lookup"><span data-stu-id="5c6a3-109">0x3A15</span></span>  <br/> |
|<span data-ttu-id="5c6a3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5c6a3-110">Data type:</span></span>  <br/> |<span data-ttu-id="5c6a3-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5c6a3-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5c6a3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5c6a3-112">Area:</span></span>  <br/> |<span data-ttu-id="5c6a3-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="5c6a3-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5c6a3-114">注解</span><span class="sxs-lookup"><span data-stu-id="5c6a3-114">Remarks</span></span>

<span data-ttu-id="5c6a3-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="5c6a3-116">它们是按收件人和收件人的组织定义的。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-116">They are defined by the recipient and the recipient's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5c6a3-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="5c6a3-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5c6a3-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="5c6a3-118">Protocol specifications</span></span>

<span data-ttu-id="5c6a3-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5c6a3-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5c6a3-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5c6a3-121">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5c6a3-121">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5c6a3-122">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5c6a3-123">头文件</span><span class="sxs-lookup"><span data-stu-id="5c6a3-123">Header files</span></span>

<span data-ttu-id="5c6a3-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5c6a3-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="5c6a3-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="5c6a3-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5c6a3-126">Mapitags.h</span></span>
  
> <span data-ttu-id="5c6a3-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5c6a3-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5c6a3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c6a3-128">See also</span></span>



[<span data-ttu-id="5c6a3-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5c6a3-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5c6a3-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5c6a3-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5c6a3-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5c6a3-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5c6a3-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5c6a3-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

