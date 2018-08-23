---
title: PidTagListSubscribe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListSubscribe
api_type:
- HeaderDef
ms.assetid: 97387a82-8e40-4c76-818c-2229fac12e01
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4408bbc9461d11859292c1d4c356c2323598eb7b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584224"
---
# <a name="pidtaglistsubscribe-canonical-property"></a><span data-ttu-id="ba5db-103">PidTagListSubscribe 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba5db-103">PidTagListSubscribe Canonical Property</span></span>

  
  
<span data-ttu-id="ba5db-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba5db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba5db-105">包含多用途 Internet 邮件扩展 (MIME) 消息的列表订阅标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="ba5db-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's List-Subscribe header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ba5db-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ba5db-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ba5db-107">PR_LIST_SUBSCRIBE，PR_LIST_SUBSCRIBE_A，PR_LIST_SUBSCRIBE_W</span><span class="sxs-lookup"><span data-stu-id="ba5db-107">PR_LIST_SUBSCRIBE, PR_LIST_SUBSCRIBE_A, PR_LIST_SUBSCRIBE_W</span></span>  <br/> |
|<span data-ttu-id="ba5db-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ba5db-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ba5db-109">0x1044</span><span class="sxs-lookup"><span data-stu-id="ba5db-109">0x1044</span></span>  <br/> |
|<span data-ttu-id="ba5db-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ba5db-110">Data type:</span></span>  <br/> |<span data-ttu-id="ba5db-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ba5db-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ba5db-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ba5db-112">Area:</span></span>  <br/> |<span data-ttu-id="ba5db-113">其他</span><span class="sxs-lookup"><span data-stu-id="ba5db-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ba5db-114">注解</span><span class="sxs-lookup"><span data-stu-id="ba5db-114">Remarks</span></span>

<span data-ttu-id="ba5db-115">要生成列表订阅头字段中，客户端必须将这些属性的值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="ba5db-115">To generate a List-Subscribe header field, clients must set the value of these properties to the desired value.</span></span> <span data-ttu-id="ba5db-116">MIME 作者必须将这些属性的值复制到的列表订阅标头字段。</span><span class="sxs-lookup"><span data-stu-id="ba5db-116">MIME writers must copy the value of these properties to the List-Subscribe header field.</span></span>
  
<span data-ttu-id="ba5db-117">若要设置类似于与服务器相关的属性的值，MIME 客户端必须编写指定下表中的标题字段。</span><span class="sxs-lookup"><span data-stu-id="ba5db-117">To set the value of server-related properties like these, MIME clients must write the header fields as specified in the following table.</span></span>
  
|<span data-ttu-id="ba5db-118">**属性**</span><span class="sxs-lookup"><span data-stu-id="ba5db-118">**Property**</span></span>|<span data-ttu-id="ba5db-119">**首选标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="ba5db-119">**Preferred header field name**</span></span>|<span data-ttu-id="ba5db-120">**备用标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="ba5db-120">**Alternate header field name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba5db-121">**PidTagListSubscribe**</span><span class="sxs-lookup"><span data-stu-id="ba5db-121">**PidTagListSubscribe**</span></span> <br/> |<span data-ttu-id="ba5db-122">列表订阅</span><span class="sxs-lookup"><span data-stu-id="ba5db-122">List-Subscribe</span></span>  <br/> |<span data-ttu-id="ba5db-123">X 列表订阅</span><span class="sxs-lookup"><span data-stu-id="ba5db-123">X-List-Subscribe</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ba5db-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="ba5db-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ba5db-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="ba5db-125">Protocol specifications</span></span>

<span data-ttu-id="ba5db-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba5db-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba5db-127">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ba5db-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ba5db-128">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba5db-128">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba5db-129">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="ba5db-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ba5db-130">头文件</span><span class="sxs-lookup"><span data-stu-id="ba5db-130">Header files</span></span>

<span data-ttu-id="ba5db-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ba5db-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="ba5db-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ba5db-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="ba5db-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ba5db-133">Mapitags.h</span></span>
  
> <span data-ttu-id="ba5db-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ba5db-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ba5db-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba5db-135">See also</span></span>



[<span data-ttu-id="ba5db-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ba5db-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ba5db-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba5db-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ba5db-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ba5db-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ba5db-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ba5db-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

