---
title: PidTagListUnsubscribe 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagListUnsubscribe
api_type:
- HeaderDef
ms.assetid: 4e6bfbc7-7586-43cc-9380-daa0fe3d85a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e057ab2ca0c75d5c0d749ebde8f1bdfb4f1ae66a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278877"
---
# <a name="pidtaglistunsubscribe-canonical-property"></a><span data-ttu-id="2013b-103">PidTagListUnsubscribe 规范属性</span><span class="sxs-lookup"><span data-stu-id="2013b-103">PidTagListUnsubscribe Canonical Property</span></span>

  
  
<span data-ttu-id="2013b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2013b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2013b-105">包含多用途 Internet 邮件扩展 (MIME) 邮件的列表取消订阅标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="2013b-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's List-Unsubscribe header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2013b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2013b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2013b-107">PR_LIST_UNSUBSCRIBE、PR_LIST_UNSUBSCRIBE_A、PR_LIST_UNSUBSCRIBE_W</span><span class="sxs-lookup"><span data-stu-id="2013b-107">PR_LIST_UNSUBSCRIBE, PR_LIST_UNSUBSCRIBE_A, PR_LIST_UNSUBSCRIBE_W</span></span>  <br/> |
|<span data-ttu-id="2013b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2013b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2013b-109">0x1045</span><span class="sxs-lookup"><span data-stu-id="2013b-109">0x1045</span></span>  <br/> |
|<span data-ttu-id="2013b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2013b-110">Data type:</span></span>  <br/> |<span data-ttu-id="2013b-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2013b-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2013b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2013b-112">Area:</span></span>  <br/> |<span data-ttu-id="2013b-113">其他</span><span class="sxs-lookup"><span data-stu-id="2013b-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2013b-114">注解</span><span class="sxs-lookup"><span data-stu-id="2013b-114">Remarks</span></span>

<span data-ttu-id="2013b-115">若要生成列表取消订阅标头字段, 客户端必须将这些属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="2013b-115">To generate a List-Unsubscribe header field, clients must set these properties to the desired value.</span></span> <span data-ttu-id="2013b-116">MIME 编写器必须将这些属性的值复制到列表取消订阅标头字段。</span><span class="sxs-lookup"><span data-stu-id="2013b-116">MIME writers must copy the value of these properties to the List-Unsubscribe header field.</span></span>
  
<span data-ttu-id="2013b-117">若要设置这些列表服务器相关属性的值, MIME 客户端必须按下表所指定的方式写入头字段。</span><span class="sxs-lookup"><span data-stu-id="2013b-117">To set the value of these list server-related properties, MIME clients must write the header fields as specified in the following table.</span></span>
  
|<span data-ttu-id="2013b-118">**Property**</span><span class="sxs-lookup"><span data-stu-id="2013b-118">**Property**</span></span>|<span data-ttu-id="2013b-119">**首选标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="2013b-119">**Preferred header field name**</span></span>|<span data-ttu-id="2013b-120">**备用标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="2013b-120">**Alternate header field name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2013b-121">**PR_LIST_UNSUBSCRIBE**</span><span class="sxs-lookup"><span data-stu-id="2013b-121">**PR_LIST_UNSUBSCRIBE**</span></span> <br/> |<span data-ttu-id="2013b-122">列表-取消订阅</span><span class="sxs-lookup"><span data-stu-id="2013b-122">List-Unsubscribe</span></span>  <br/> |<span data-ttu-id="2013b-123">X-列表-取消订阅</span><span class="sxs-lookup"><span data-stu-id="2013b-123">X-List-Unsubscribe</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="2013b-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="2013b-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2013b-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="2013b-125">Protocol specifications</span></span>

<span data-ttu-id="2013b-126">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2013b-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2013b-127">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2013b-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2013b-128">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2013b-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2013b-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="2013b-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2013b-130">头文件</span><span class="sxs-lookup"><span data-stu-id="2013b-130">Header files</span></span>

<span data-ttu-id="2013b-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2013b-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="2013b-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2013b-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="2013b-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="2013b-133">Mapitags.h</span></span>
  
> <span data-ttu-id="2013b-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2013b-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2013b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2013b-135">See also</span></span>



[<span data-ttu-id="2013b-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2013b-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2013b-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2013b-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2013b-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2013b-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2013b-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2013b-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

