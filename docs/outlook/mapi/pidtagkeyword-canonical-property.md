---
title: PidTagKeyword 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagKeyword
api_type:
- HeaderDef
ms.assetid: 8dbfb22d-93db-468c-b2a4-eaa2b545bd61
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 190135f64ad02a2b6c560dd819f1749286f329a6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591315"
---
# <a name="pidtagkeyword-canonical-property"></a><span data-ttu-id="65e27-103">PidTagKeyword 规范属性</span><span class="sxs-lookup"><span data-stu-id="65e27-103">PidTagKeyword Canonical Property</span></span>

  
  
<span data-ttu-id="65e27-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65e27-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65e27-105">包含标识为收件人的系统管理员收件人的关键字。</span><span class="sxs-lookup"><span data-stu-id="65e27-105">Contains a keyword that identifies the recipient to the recipient's system administrator.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="65e27-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="65e27-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="65e27-107">PR_KEYWORD，PR_KEYWORD_A，PR_KEYWORD_W</span><span class="sxs-lookup"><span data-stu-id="65e27-107">PR_KEYWORD, PR_KEYWORD_A, PR_KEYWORD_W</span></span>  <br/> |
|<span data-ttu-id="65e27-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="65e27-108">Identifier:</span></span>  <br/> |<span data-ttu-id="65e27-109">0x3A0B</span><span class="sxs-lookup"><span data-stu-id="65e27-109">0x3A0B</span></span>  <br/> |
|<span data-ttu-id="65e27-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="65e27-110">Data type:</span></span>  <br/> |<span data-ttu-id="65e27-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="65e27-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="65e27-112">区域：</span><span class="sxs-lookup"><span data-stu-id="65e27-112">Area:</span></span>  <br/> |<span data-ttu-id="65e27-113">Address</span><span class="sxs-lookup"><span data-stu-id="65e27-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="65e27-114">注解</span><span class="sxs-lookup"><span data-stu-id="65e27-114">Remarks</span></span>

<span data-ttu-id="65e27-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="65e27-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="65e27-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="65e27-116">They are defined by the recipient and their organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="65e27-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="65e27-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="65e27-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="65e27-118">Protocol specifications</span></span>

<span data-ttu-id="65e27-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="65e27-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="65e27-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="65e27-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="65e27-121">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="65e27-121">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="65e27-122">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="65e27-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="65e27-123">头文件</span><span class="sxs-lookup"><span data-stu-id="65e27-123">Header files</span></span>

<span data-ttu-id="65e27-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="65e27-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="65e27-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="65e27-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="65e27-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="65e27-126">Mapitags.h</span></span>
  
> <span data-ttu-id="65e27-127">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="65e27-127">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="65e27-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65e27-128">See also</span></span>



[<span data-ttu-id="65e27-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="65e27-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="65e27-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="65e27-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="65e27-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="65e27-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="65e27-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="65e27-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

