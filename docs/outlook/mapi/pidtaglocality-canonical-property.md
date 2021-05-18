---
title: PidTagLocality 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLocality
api_type:
- HeaderDef
ms.assetid: a918b596-a335-47a0-9d1c-109a0b0812a2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e4c381c6fd8148a13d493e916e6a372f75647eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278720"
---
# <a name="pidtaglocality-canonical-property"></a><span data-ttu-id="d5825-103">PidTagLocality 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5825-103">PidTagLocality Canonical Property</span></span>

  
  
<span data-ttu-id="d5825-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5825-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5825-105">包含收件人区域的名称，如县或城市。</span><span class="sxs-lookup"><span data-stu-id="d5825-105">Contains the name of the recipient's locality, such as the town or city.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d5825-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d5825-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d5825-107">PR_LOCALITY、PR_LOCALITY_A、PR_LOCALITY_W、PR_BUSINESS_ADDRESS_LOCALITY、PR_BUSINESS_ADDRESS_LOCALITY_A、PR_BUSINESS_ADDRESS_LOCALITY_W</span><span class="sxs-lookup"><span data-stu-id="d5825-107">PR_LOCALITY, PR_LOCALITY_A, PR_LOCALITY_W, PR_BUSINESS_ADDRESS_LOCALITY, PR_BUSINESS_ADDRESS_LOCALITY_A, PR_BUSINESS_ADDRESS_LOCALITY_W</span></span>  <br/> |
|<span data-ttu-id="d5825-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d5825-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d5825-109">0x3A27</span><span class="sxs-lookup"><span data-stu-id="d5825-109">0x3A27</span></span>  <br/> |
|<span data-ttu-id="d5825-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d5825-110">Data type:</span></span>  <br/> |<span data-ttu-id="d5825-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="d5825-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="d5825-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d5825-112">Area:</span></span>  <br/> |<span data-ttu-id="d5825-113">地址</span><span class="sxs-lookup"><span data-stu-id="d5825-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5825-114">备注</span><span class="sxs-lookup"><span data-stu-id="d5825-114">Remarks</span></span>

<span data-ttu-id="d5825-115">这些属性为收件人提供标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="d5825-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="d5825-116">它们由收件人及其组织定义。</span><span class="sxs-lookup"><span data-stu-id="d5825-116">Theys are defined by the recipient and their organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d5825-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d5825-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d5825-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="d5825-118">Protocol specifications</span></span>

<span data-ttu-id="d5825-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5825-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d5825-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="d5825-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d5825-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5825-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d5825-122">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d5825-122">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="d5825-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d5825-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d5825-124">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="d5825-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d5825-125">头文件</span><span class="sxs-lookup"><span data-stu-id="d5825-125">Header files</span></span>

<span data-ttu-id="d5825-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d5825-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="d5825-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d5825-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="d5825-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d5825-128">Mapitags.h</span></span>
  
> <span data-ttu-id="d5825-129">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d5825-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d5825-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5825-130">See also</span></span>



[<span data-ttu-id="d5825-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d5825-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d5825-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5825-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d5825-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d5825-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d5825-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d5825-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

