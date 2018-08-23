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
ms.openlocfilehash: a9a513d5044a026475077ea7d4b86821e1c4cd82
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569167"
---
# <a name="pidtaggeneration-canonical-property"></a><span data-ttu-id="c3e0f-103">PidTagGeneration 规范属性</span><span class="sxs-lookup"><span data-stu-id="c3e0f-103">PidTagGeneration Canonical Property</span></span>

  
  
<span data-ttu-id="c3e0f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3e0f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3e0f-105">包含的代缩写，遵循收件人的完整名称。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-105">Contains a generational abbreviation that follows the full name of the recipient.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c3e0f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c3e0f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c3e0f-107">PR_GENERATION，PR_GENERATION_A，PR_GENERATION_W</span><span class="sxs-lookup"><span data-stu-id="c3e0f-107">PR_GENERATION, PR_GENERATION_A, PR_GENERATION_W</span></span>  <br/> |
|<span data-ttu-id="c3e0f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c3e0f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c3e0f-109">0x3A05</span><span class="sxs-lookup"><span data-stu-id="c3e0f-109">0x3A05</span></span>  <br/> |
|<span data-ttu-id="c3e0f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c3e0f-110">Data type:</span></span>  <br/> |<span data-ttu-id="c3e0f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c3e0f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="c3e0f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c3e0f-112">Area:</span></span>  <br/> |<span data-ttu-id="c3e0f-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="c3e0f-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c3e0f-114">注解</span><span class="sxs-lookup"><span data-stu-id="c3e0f-114">Remarks</span></span>

<span data-ttu-id="c3e0f-115">这些属性提供标识和访问有关收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-115">These properties provide identification and access information about a recipient.</span></span> <span data-ttu-id="c3e0f-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="c3e0f-117">常见的值包括先生，sr。 和 III。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-117">Common values include Jr., Sr., and III.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c3e0f-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="c3e0f-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c3e0f-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="c3e0f-119">Protocol specifications</span></span>

<span data-ttu-id="c3e0f-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3e0f-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c3e0f-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c3e0f-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3e0f-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c3e0f-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="c3e0f-124">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3e0f-124">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c3e0f-125">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-125">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c3e0f-126">头文件</span><span class="sxs-lookup"><span data-stu-id="c3e0f-126">Header files</span></span>

<span data-ttu-id="c3e0f-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c3e0f-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="c3e0f-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="c3e0f-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c3e0f-129">Mapitags.h</span></span>
  
> <span data-ttu-id="c3e0f-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c3e0f-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c3e0f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3e0f-131">See also</span></span>



[<span data-ttu-id="c3e0f-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c3e0f-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c3e0f-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c3e0f-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c3e0f-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c3e0f-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c3e0f-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c3e0f-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

