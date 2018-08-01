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
ms.openlocfilehash: dcfaf9f4e71a13a8697da0cac98f7ea9cc3d8708
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777724"
---
# <a name="pidtagimplicitconversionprohibited-canonical-property"></a><span data-ttu-id="9f14f-103">PidTagImplicitConversionProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f14f-103">PidTagImplicitConversionProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="9f14f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9f14f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9f14f-105">如果邮件传输代理 (MTA) 禁止发出隐式消息文本转换，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9f14f-105">Contains TRUE if a message transfer agent (MTA) is prohibited from making implicit message text conversions.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9f14f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9f14f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9f14f-107">PR_IMPLICIT_CONVERSION_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="9f14f-107">PR_IMPLICIT_CONVERSION_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="9f14f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9f14f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9f14f-109">0x0016</span><span class="sxs-lookup"><span data-stu-id="9f14f-109">0x0016</span></span>  <br/> |
|<span data-ttu-id="9f14f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9f14f-110">Data type:</span></span>  <br/> |<span data-ttu-id="9f14f-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="9f14f-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="9f14f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9f14f-112">Area:</span></span>  <br/> |<span data-ttu-id="9f14f-113">Server</span><span class="sxs-lookup"><span data-stu-id="9f14f-113">Server</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f14f-114">说明</span><span class="sxs-lookup"><span data-stu-id="9f14f-114">Remarks</span></span>

<span data-ttu-id="9f14f-115">如果此属性为 TRUE，则在邮件系统必须不执行任何内容转换对邮件除非明确请求**PR_EXPLICIT_CONVERSION** ([PidTagExplicitConversion](pidtagexplicitconversion-canonical-property.md)) 属性分别为每个收件人。</span><span class="sxs-lookup"><span data-stu-id="9f14f-115">If this property is TRUE, the messaging system must not perform any content conversion on the message unless it is explicitly requested on a per-recipient basis with the **PR_EXPLICIT_CONVERSION** ([PidTagExplicitConversion](pidtagexplicitconversion-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9f14f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="9f14f-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9f14f-117">头文件</span><span class="sxs-lookup"><span data-stu-id="9f14f-117">Header files</span></span>

<span data-ttu-id="9f14f-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9f14f-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="9f14f-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9f14f-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="9f14f-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9f14f-120">Mapitags.h</span></span>
  
> <span data-ttu-id="9f14f-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9f14f-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9f14f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f14f-122">See also</span></span>



[<span data-ttu-id="9f14f-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9f14f-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9f14f-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f14f-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9f14f-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9f14f-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9f14f-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9f14f-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

