---
title: PidTagAutoForwarded 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAutoForwarded
api_type:
- HeaderDef
ms.assetid: 1ba40cc2-ba27-4d75-9682-c536cf3a0d58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 25d1bb121df6470f5038a2106587e3f5b37f6bb7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386360"
---
# <a name="pidtagautoforwarded-canonical-property"></a><span data-ttu-id="28834-103">PidTagAutoForwarded 规范属性</span><span class="sxs-lookup"><span data-stu-id="28834-103">PidTagAutoForwarded Canonical Property</span></span>

  
  
<span data-ttu-id="28834-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28834-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28834-105">如果客户端请求 X-MS-Exchange-组织的自动，转发头字段中，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="28834-105">Contains TRUE if the client requests an X-MS-Exchange-Organization-AutoForwarded header field.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="28834-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="28834-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="28834-107">PR_AUTO_FORWARDED</span><span class="sxs-lookup"><span data-stu-id="28834-107">PR_AUTO_FORWARDED</span></span>  <br/> |
|<span data-ttu-id="28834-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="28834-108">Identifier:</span></span>  <br/> |<span data-ttu-id="28834-109">0x0005</span><span class="sxs-lookup"><span data-stu-id="28834-109">0x0005</span></span>  <br/> |
|<span data-ttu-id="28834-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="28834-110">Data type:</span></span>  <br/> |<span data-ttu-id="28834-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="28834-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="28834-112">区域：</span><span class="sxs-lookup"><span data-stu-id="28834-112">Area:</span></span>  <br/> |<span data-ttu-id="28834-113">常规报告</span><span class="sxs-lookup"><span data-stu-id="28834-113">General reporting</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="28834-114">说明</span><span class="sxs-lookup"><span data-stu-id="28834-114">Remarks</span></span>

<span data-ttu-id="28834-115">如果此属性设置为 FALSE 或不使用，将创建没有 X-MS-Exchange-组织的自动，转发标头字段。</span><span class="sxs-lookup"><span data-stu-id="28834-115">If this property is set to FALSE or not used, no X-MS-Exchange-Organization-AutoForwarded header field will be created.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="28834-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="28834-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="28834-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="28834-117">Protocol specifications</span></span>

<span data-ttu-id="28834-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="28834-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="28834-119">定义由 MS OXO 前缀文档描述的对象中的使用每个属性。</span><span class="sxs-lookup"><span data-stu-id="28834-119">Defines each property that is used in the objects that are described by MS-OXO-prefixed documents.</span></span>
    
<span data-ttu-id="28834-120">[[MS OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="28834-120">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="28834-121">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="28834-121">Converts from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="28834-122">头文件</span><span class="sxs-lookup"><span data-stu-id="28834-122">Header files</span></span>

<span data-ttu-id="28834-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="28834-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="28834-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="28834-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="28834-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="28834-125">Mapitags.h</span></span>
  
> <span data-ttu-id="28834-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="28834-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="28834-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28834-127">See also</span></span>



[<span data-ttu-id="28834-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="28834-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="28834-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="28834-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="28834-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="28834-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="28834-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="28834-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

