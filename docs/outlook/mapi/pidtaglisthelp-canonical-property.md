---
title: PidTagListHelp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListHelp
api_type:
- HeaderDef
ms.assetid: 403324b8-c992-4823-aa0f-0414b283debc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b523277a3865e62e8ed95883213b28d2155ffb54
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594794"
---
# <a name="pidtaglisthelp-canonical-property"></a><span data-ttu-id="439eb-103">PidTagListHelp 规范属性</span><span class="sxs-lookup"><span data-stu-id="439eb-103">PidTagListHelp Canonical Property</span></span>

  
  
<span data-ttu-id="439eb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="439eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="439eb-105">包含多用途 Internet 邮件扩展 (MIME) 消息的列表帮助标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="439eb-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's List-Help header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="439eb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="439eb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="439eb-107">PR_LIST_HELP，PR_LIST_HELP_A，PR_LIST_HELP_W</span><span class="sxs-lookup"><span data-stu-id="439eb-107">PR_LIST_HELP, PR_LIST_HELP_A, PR_LIST_HELP_W</span></span>  <br/> |
|<span data-ttu-id="439eb-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="439eb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="439eb-109">0x1043</span><span class="sxs-lookup"><span data-stu-id="439eb-109">0x1043</span></span>  <br/> |
|<span data-ttu-id="439eb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="439eb-110">Data type:</span></span>  <br/> |<span data-ttu-id="439eb-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="439eb-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="439eb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="439eb-112">Area:</span></span>  <br/> |<span data-ttu-id="439eb-113">其他</span><span class="sxs-lookup"><span data-stu-id="439eb-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="439eb-114">注解</span><span class="sxs-lookup"><span data-stu-id="439eb-114">Remarks</span></span>

<span data-ttu-id="439eb-115">若要生成列表帮助头字段，客户端必须将**PR_LIST_HELP**或相关联的属性的值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="439eb-115">To generate a List-Help header field, clients must set the value of **PR_LIST_HELP** or an associated property to the desired value.</span></span> <span data-ttu-id="439eb-116">MIME 作者必须将此值复制到列表帮助标头字段。</span><span class="sxs-lookup"><span data-stu-id="439eb-116">MIME writers must copy this value to the List-Help header field.</span></span> 
  
<span data-ttu-id="439eb-117">若要设置这些列表服务器相关的属性的值，MIME 客户端必须编写为下表中指定的标题字段：</span><span class="sxs-lookup"><span data-stu-id="439eb-117">To set the value of these list server-related properties, MIME clients must write the header fields as specified in the following table:</span></span>
  
|<span data-ttu-id="439eb-118">**属性**</span><span class="sxs-lookup"><span data-stu-id="439eb-118">**Property**</span></span>|<span data-ttu-id="439eb-119">**首选标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="439eb-119">**Preferred header field name**</span></span>|<span data-ttu-id="439eb-120">**备用标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="439eb-120">**Alternate header field name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="439eb-121">**PR_LIST_HELP**</span><span class="sxs-lookup"><span data-stu-id="439eb-121">**PR_LIST_HELP**</span></span> <br/> |<span data-ttu-id="439eb-122">列表帮助</span><span class="sxs-lookup"><span data-stu-id="439eb-122">List-Help</span></span>  <br/> |<span data-ttu-id="439eb-123">X-列表-帮助</span><span class="sxs-lookup"><span data-stu-id="439eb-123">X-List-Help</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="439eb-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="439eb-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="439eb-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="439eb-125">Protocol specifications</span></span>

<span data-ttu-id="439eb-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="439eb-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="439eb-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="439eb-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="439eb-128">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="439eb-128">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="439eb-129">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="439eb-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="439eb-130">头文件</span><span class="sxs-lookup"><span data-stu-id="439eb-130">Header files</span></span>

<span data-ttu-id="439eb-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="439eb-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="439eb-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="439eb-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="439eb-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="439eb-133">Mapitags.h</span></span>
  
> <span data-ttu-id="439eb-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="439eb-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="439eb-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="439eb-135">See also</span></span>



[<span data-ttu-id="439eb-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="439eb-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="439eb-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="439eb-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="439eb-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="439eb-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="439eb-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="439eb-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

