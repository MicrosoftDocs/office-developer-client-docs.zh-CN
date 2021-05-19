---
title: PidTagImplicitConversionProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagImplicitConversionProhibited
api_type:
- HeaderDef
ms.assetid: c6cb5a86-0105-4743-9f8e-b832e898da52
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0e18ef529b65317abd9446408ed73638c792809
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420666"
---
# <a name="pidtagimplicitconversionprohibited-canonical-property"></a><span data-ttu-id="5d408-103">PidTagImplicitConversionProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d408-103">PidTagImplicitConversionProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="5d408-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d408-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d408-105">如果禁止邮件传输代理 (MTA) 进行隐式邮件文本转换，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5d408-105">Contains TRUE if a message transfer agent (MTA) is prohibited from making implicit message text conversions.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d408-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5d408-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5d408-107">PR_IMPLICIT_CONVERSION_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="5d408-107">PR_IMPLICIT_CONVERSION_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="5d408-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5d408-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5d408-109">0x0016</span><span class="sxs-lookup"><span data-stu-id="5d408-109">0x0016</span></span>  <br/> |
|<span data-ttu-id="5d408-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5d408-110">Data type:</span></span>  <br/> |<span data-ttu-id="5d408-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="5d408-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="5d408-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5d408-112">Area:</span></span>  <br/> |<span data-ttu-id="5d408-113">服务器</span><span class="sxs-lookup"><span data-stu-id="5d408-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d408-114">备注</span><span class="sxs-lookup"><span data-stu-id="5d408-114">Remarks</span></span>

<span data-ttu-id="5d408-115">如果此属性为 TRUE，则邮件系统不得对邮件执行任何内容转换，除非使用 **PR_EXPLICIT_CONVERSION** ([PidTagExplicitConversion](pidtagexplicitconversion-canonical-property.md)) 属性按收件人显式请求。</span><span class="sxs-lookup"><span data-stu-id="5d408-115">If this property is TRUE, the messaging system must not perform any content conversion on the message unless it is explicitly requested on a per-recipient basis with the **PR_EXPLICIT_CONVERSION** ([PidTagExplicitConversion](pidtagexplicitconversion-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5d408-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5d408-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5d408-117">头文件</span><span class="sxs-lookup"><span data-stu-id="5d408-117">Header files</span></span>

<span data-ttu-id="5d408-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5d408-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="5d408-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5d408-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="5d408-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5d408-120">Mapitags.h</span></span>
  
> <span data-ttu-id="5d408-121">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5d408-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5d408-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d408-122">See also</span></span>



[<span data-ttu-id="5d408-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5d408-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5d408-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d408-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5d408-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5d408-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5d408-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d408-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

