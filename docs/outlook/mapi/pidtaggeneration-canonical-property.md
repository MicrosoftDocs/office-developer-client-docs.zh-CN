---
title: PidTagGeneration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagGeneration
api_type:
- HeaderDef
ms.assetid: 81c2e479-84a1-42ba-a9ce-25e3fc8d80cb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4f13aa14569daeb60271ea6d8645af6f6fe3bcd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777664"
---
# <a name="pidtaggeneration-canonical-property"></a><span data-ttu-id="35298-103">PidTagGeneration 规范属性</span><span class="sxs-lookup"><span data-stu-id="35298-103">PidTagGeneration Canonical Property</span></span>

  
  
<span data-ttu-id="35298-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="35298-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="35298-105">包含的代缩写，遵循收件人的完整名称。</span><span class="sxs-lookup"><span data-stu-id="35298-105">Contains a generational abbreviation that follows the full name of the recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="35298-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="35298-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="35298-107">PR_GENERATION，PR_GENERATION_A，PR_GENERATION_W</span><span class="sxs-lookup"><span data-stu-id="35298-107">PR_GENERATION, PR_GENERATION_A, PR_GENERATION_W</span></span>  <br/> |
|<span data-ttu-id="35298-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="35298-108">Identifier:</span></span>  <br/> |<span data-ttu-id="35298-109">0x3A05</span><span class="sxs-lookup"><span data-stu-id="35298-109">0x3A05</span></span>  <br/> |
|<span data-ttu-id="35298-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="35298-110">Data type:</span></span>  <br/> |<span data-ttu-id="35298-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="35298-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="35298-112">区域：</span><span class="sxs-lookup"><span data-stu-id="35298-112">Area:</span></span>  <br/> |<span data-ttu-id="35298-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="35298-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="35298-114">说明</span><span class="sxs-lookup"><span data-stu-id="35298-114">Remarks</span></span>

<span data-ttu-id="35298-115">这些属性提供标识和访问有关收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="35298-115">These properties provide identification and access information about a recipient.</span></span> <span data-ttu-id="35298-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="35298-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="35298-117">常见的值包括先生，sr。 和 III。</span><span class="sxs-lookup"><span data-stu-id="35298-117">Common values include Jr., Sr., and III.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="35298-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="35298-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="35298-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="35298-119">Protocol specifications</span></span>

<span data-ttu-id="35298-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35298-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35298-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="35298-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="35298-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35298-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35298-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="35298-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="35298-124">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="35298-124">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="35298-125">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="35298-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="35298-126">头文件</span><span class="sxs-lookup"><span data-stu-id="35298-126">Header files</span></span>

<span data-ttu-id="35298-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="35298-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="35298-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="35298-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="35298-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="35298-129">Mapitags.h</span></span>
  
> <span data-ttu-id="35298-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="35298-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="35298-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35298-131">See also</span></span>



[<span data-ttu-id="35298-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="35298-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="35298-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="35298-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="35298-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="35298-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="35298-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="35298-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

