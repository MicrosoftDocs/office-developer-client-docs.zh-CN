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
ms.openlocfilehash: 588747205ee3922fef7b107dc024f074a6ee527e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279627"
---
# <a name="pidtaglisthelp-canonical-property"></a><span data-ttu-id="abcad-103">PidTagListHelp 规范属性</span><span class="sxs-lookup"><span data-stu-id="abcad-103">PidTagListHelp Canonical Property</span></span>

  
  
<span data-ttu-id="abcad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="abcad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="abcad-105">包含多用途 Internet 邮件扩展 (MIME) 邮件的List-Help字段。</span><span class="sxs-lookup"><span data-stu-id="abcad-105">Contains the value of a Multipurpose Internet Mail Extensions (MIME) message's List-Help header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="abcad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="abcad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="abcad-107">PR_LIST_HELP、PR_LIST_HELP_A、PR_LIST_HELP_W</span><span class="sxs-lookup"><span data-stu-id="abcad-107">PR_LIST_HELP, PR_LIST_HELP_A, PR_LIST_HELP_W</span></span>  <br/> |
|<span data-ttu-id="abcad-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="abcad-108">Identifier:</span></span>  <br/> |<span data-ttu-id="abcad-109">0x1043</span><span class="sxs-lookup"><span data-stu-id="abcad-109">0x1043</span></span>  <br/> |
|<span data-ttu-id="abcad-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="abcad-110">Data type:</span></span>  <br/> |<span data-ttu-id="abcad-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="abcad-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="abcad-112">区域：</span><span class="sxs-lookup"><span data-stu-id="abcad-112">Area:</span></span>  <br/> |<span data-ttu-id="abcad-113">其他</span><span class="sxs-lookup"><span data-stu-id="abcad-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="abcad-114">备注</span><span class="sxs-lookup"><span data-stu-id="abcad-114">Remarks</span></span>

<span data-ttu-id="abcad-115">若要生成List-Help字段，客户端必须将 PR_LIST_HELP 或关联的属性的值设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="abcad-115">To generate a List-Help header field, clients must set the value of **PR_LIST_HELP** or an associated property to the desired value.</span></span> <span data-ttu-id="abcad-116">MIME 编写器必须将此值复制到List-Help字段。</span><span class="sxs-lookup"><span data-stu-id="abcad-116">MIME writers must copy this value to the List-Help header field.</span></span> 
  
<span data-ttu-id="abcad-117">若要设置这些列表服务器相关属性的值，MIME 客户端必须编写下表中指定的头字段：</span><span class="sxs-lookup"><span data-stu-id="abcad-117">To set the value of these list server-related properties, MIME clients must write the header fields as specified in the following table:</span></span>
  
|<span data-ttu-id="abcad-118">**Property**</span><span class="sxs-lookup"><span data-stu-id="abcad-118">**Property**</span></span>|<span data-ttu-id="abcad-119">**首选标题字段名称**</span><span class="sxs-lookup"><span data-stu-id="abcad-119">**Preferred header field name**</span></span>|<span data-ttu-id="abcad-120">**备用标头字段名称**</span><span class="sxs-lookup"><span data-stu-id="abcad-120">**Alternate header field name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abcad-121">**PR_LIST_HELP**</span><span class="sxs-lookup"><span data-stu-id="abcad-121">**PR_LIST_HELP**</span></span> <br/> |<span data-ttu-id="abcad-122">List-Help</span><span class="sxs-lookup"><span data-stu-id="abcad-122">List-Help</span></span>  <br/> |<span data-ttu-id="abcad-123">X-List-Help</span><span class="sxs-lookup"><span data-stu-id="abcad-123">X-List-Help</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="abcad-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="abcad-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="abcad-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="abcad-125">Protocol specifications</span></span>

<span data-ttu-id="abcad-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="abcad-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="abcad-127">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="abcad-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="abcad-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="abcad-128">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="abcad-129">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="abcad-129">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="abcad-130">头文件</span><span class="sxs-lookup"><span data-stu-id="abcad-130">Header files</span></span>

<span data-ttu-id="abcad-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="abcad-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="abcad-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="abcad-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="abcad-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="abcad-133">Mapitags.h</span></span>
  
> <span data-ttu-id="abcad-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="abcad-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="abcad-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abcad-135">See also</span></span>



[<span data-ttu-id="abcad-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="abcad-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="abcad-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="abcad-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="abcad-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="abcad-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="abcad-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="abcad-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

