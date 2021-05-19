---
title: PidTagTitle 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTitle
api_type:
- COM
ms.assetid: f35bbcc3-15dd-40ab-9bf4-bdb21f95d464
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2501ea7c4be08b0bec3c2d65e6a504df47dfc488
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358763"
---
# <a name="pidtagtitle-canonical-property"></a><span data-ttu-id="27ac9-103">PidTagTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="27ac9-103">PidTagTitle Canonical Property</span></span>

  
  
<span data-ttu-id="27ac9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27ac9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27ac9-105">包含收件人的工作职务。</span><span class="sxs-lookup"><span data-stu-id="27ac9-105">Contains the recipient's job title.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="27ac9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="27ac9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="27ac9-107">PR_TITLE、PR_TITLE_A、PR_TITLE_W</span><span class="sxs-lookup"><span data-stu-id="27ac9-107">PR_TITLE, PR_TITLE_A, PR_TITLE_W</span></span>  <br/> |
|<span data-ttu-id="27ac9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="27ac9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="27ac9-109">0x3A17</span><span class="sxs-lookup"><span data-stu-id="27ac9-109">0x3A17</span></span>  <br/> |
|<span data-ttu-id="27ac9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="27ac9-110">Data type:</span></span>  <br/> |<span data-ttu-id="27ac9-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="27ac9-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="27ac9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="27ac9-112">Area:</span></span>  <br/> |<span data-ttu-id="27ac9-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="27ac9-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="27ac9-114">备注</span><span class="sxs-lookup"><span data-stu-id="27ac9-114">Remarks</span></span>

<span data-ttu-id="27ac9-115">这些属性为收件人提供标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="27ac9-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="27ac9-116">它们由收件人和收件人的组织定义。</span><span class="sxs-lookup"><span data-stu-id="27ac9-116">They are defined by the recipient and the recipient's organization.</span></span> 
  
<span data-ttu-id="27ac9-117">这些属性通常用于指示收件人的正式职务（如高级程序员）而不是程序员类。</span><span class="sxs-lookup"><span data-stu-id="27ac9-117">These properties are commonly used to indicate the recipient's formal job title, such as Senior Programmer, rather than occupational class, such as programmer.</span></span> <span data-ttu-id="27ac9-118">它通常不用于"后缀"标题，如 Esq。</span><span class="sxs-lookup"><span data-stu-id="27ac9-118">It is not typically used for "suffix" titles such as Esq.</span></span> <span data-ttu-id="27ac9-119">或 DDS。</span><span class="sxs-lookup"><span data-stu-id="27ac9-119">or DDS.</span></span>
  
<span data-ttu-id="27ac9-120">此属性的常见值包括：Managing Director、Programmer II、Associate Programmer 和 Development Lead。</span><span class="sxs-lookup"><span data-stu-id="27ac9-120">Common values for this property include: Managing Director, Programmer II, Associate Professor, and Development Lead.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="27ac9-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="27ac9-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="27ac9-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="27ac9-122">Protocol specifications</span></span>

<span data-ttu-id="27ac9-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="27ac9-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="27ac9-124">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="27ac9-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="27ac9-125">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="27ac9-125">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="27ac9-126">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="27ac9-126">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="27ac9-127">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="27ac9-127">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="27ac9-128">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="27ac9-128">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="27ac9-129">头文件</span><span class="sxs-lookup"><span data-stu-id="27ac9-129">Header files</span></span>

<span data-ttu-id="27ac9-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="27ac9-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="27ac9-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="27ac9-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="27ac9-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="27ac9-132">Mapitags.h</span></span>
  
> <span data-ttu-id="27ac9-133">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="27ac9-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="27ac9-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27ac9-134">See also</span></span>



[<span data-ttu-id="27ac9-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="27ac9-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="27ac9-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="27ac9-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="27ac9-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="27ac9-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="27ac9-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="27ac9-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

