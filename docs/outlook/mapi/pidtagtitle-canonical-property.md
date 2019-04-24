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
# <a name="pidtagtitle-canonical-property"></a><span data-ttu-id="ab4c0-103">PidTagTitle 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab4c0-103">PidTagTitle Canonical Property</span></span>

  
  
<span data-ttu-id="ab4c0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab4c0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab4c0-105">包含收件人的职务。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-105">Contains the recipient's job title.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ab4c0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ab4c0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ab4c0-107">PR_TITLE、PR_TITLE_A、PR_TITLE_W</span><span class="sxs-lookup"><span data-stu-id="ab4c0-107">PR_TITLE, PR_TITLE_A, PR_TITLE_W</span></span>  <br/> |
|<span data-ttu-id="ab4c0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ab4c0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ab4c0-109">0x3A17</span><span class="sxs-lookup"><span data-stu-id="ab4c0-109">0x3A17</span></span>  <br/> |
|<span data-ttu-id="ab4c0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ab4c0-110">Data type:</span></span>  <br/> |<span data-ttu-id="ab4c0-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ab4c0-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ab4c0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ab4c0-112">Area:</span></span>  <br/> |<span data-ttu-id="ab4c0-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="ab4c0-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ab4c0-114">注解</span><span class="sxs-lookup"><span data-stu-id="ab4c0-114">Remarks</span></span>

<span data-ttu-id="ab4c0-115">这些属性可提供收件人的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="ab4c0-116">它们由收件人和收件人的组织定义。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-116">They are defined by the recipient and the recipient's organization.</span></span> 
  
<span data-ttu-id="ab4c0-117">这些属性通常用于指示收件人的正式职务 (如高级程序员), 而不是 occupational 类 (如程序员)。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-117">These properties are commonly used to indicate the recipient's formal job title, such as Senior Programmer, rather than occupational class, such as programmer.</span></span> <span data-ttu-id="ab4c0-118">它通常不用于 "后缀" 标题, 如 Esq。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-118">It is not typically used for "suffix" titles such as Esq.</span></span> <span data-ttu-id="ab4c0-119">或 DDS。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-119">or DDS.</span></span>
  
<span data-ttu-id="ab4c0-120">此属性的常见值包括: 管理导演、程序员 II、关联教授和开发主管。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-120">Common values for this property include: Managing Director, Programmer II, Associate Professor, and Development Lead.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ab4c0-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="ab4c0-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ab4c0-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="ab4c0-122">Protocol specifications</span></span>

<span data-ttu-id="ab4c0-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab4c0-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab4c0-124">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ab4c0-125">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab4c0-125">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab4c0-126">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-126">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="ab4c0-127">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab4c0-127">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ab4c0-128">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-128">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ab4c0-129">头文件</span><span class="sxs-lookup"><span data-stu-id="ab4c0-129">Header files</span></span>

<span data-ttu-id="ab4c0-130">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ab4c0-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="ab4c0-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="ab4c0-132">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ab4c0-132">Mapitags.h</span></span>
  
> <span data-ttu-id="ab4c0-133">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ab4c0-133">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab4c0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab4c0-134">See also</span></span>



[<span data-ttu-id="ab4c0-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ab4c0-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ab4c0-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ab4c0-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ab4c0-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ab4c0-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ab4c0-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ab4c0-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

