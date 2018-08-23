---
title: PidTagConversionWithLossProhibited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagConversionWithLossProhibited
api_type:
- HeaderDef
ms.assetid: a18b560a-e054-45b3-946d-6504465db5b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5d9261a9f33d77d52cfd6e448e69a2c1e8df415
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585232"
---
# <a name="pidtagconversionwithlossprohibited-canonical-property"></a><span data-ttu-id="2d497-103">PidTagConversionWithLossProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d497-103">PidTagConversionWithLossProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="2d497-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d497-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d497-105">包含 TRUE，则邮件传输代理 (MTA) 禁止进行丢失信息的文本转换的消息。</span><span class="sxs-lookup"><span data-stu-id="2d497-105">Contains TRUE if a message transfer agent (MTA) is prohibited from making message text conversions that lose information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2d497-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2d497-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2d497-107">PR_CONVERSION_WITH_LOSS_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="2d497-107">PR_CONVERSION_WITH_LOSS_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="2d497-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2d497-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2d497-109">0x000D</span><span class="sxs-lookup"><span data-stu-id="2d497-109">0x000D</span></span>  <br/> |
|<span data-ttu-id="2d497-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2d497-110">Data type:</span></span>  <br/> |<span data-ttu-id="2d497-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2d497-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="2d497-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2d497-112">Area:</span></span>  <br/> |<span data-ttu-id="2d497-113">常规配置</span><span class="sxs-lookup"><span data-stu-id="2d497-113">General configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2d497-114">注解</span><span class="sxs-lookup"><span data-stu-id="2d497-114">Remarks</span></span>

<span data-ttu-id="2d497-115">被禁止的转换类型的示例为"有损"映射 Unicode （每个字符的两个字节） 到单字节字符集。</span><span class="sxs-lookup"><span data-stu-id="2d497-115">An example of the type of conversion being prohibited is the "lossy" mapping from Unicode (two bytes per character) to a single-byte character set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2d497-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="2d497-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2d497-117">头文件</span><span class="sxs-lookup"><span data-stu-id="2d497-117">Header files</span></span>

<span data-ttu-id="2d497-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2d497-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="2d497-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2d497-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="2d497-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2d497-120">Mapitags.h</span></span>
  
> <span data-ttu-id="2d497-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2d497-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2d497-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d497-122">See also</span></span>



[<span data-ttu-id="2d497-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2d497-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2d497-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d497-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2d497-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2d497-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2d497-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2d497-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

