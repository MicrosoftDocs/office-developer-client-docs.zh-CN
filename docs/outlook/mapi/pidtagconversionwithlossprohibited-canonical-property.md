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
ms.openlocfilehash: 972df747e0ee459996b9b4da5732be1490fbd08a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417124"
---
# <a name="pidtagconversionwithlossprohibited-canonical-property"></a><span data-ttu-id="f6574-103">PidTagConversionWithLossProhibited 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6574-103">PidTagConversionWithLossProhibited Canonical Property</span></span>

  
  
<span data-ttu-id="f6574-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6574-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6574-105">如果禁止邮件传输代理 (MTA) 进行丢失信息的邮件文本转换，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f6574-105">Contains TRUE if a message transfer agent (MTA) is prohibited from making message text conversions that lose information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f6574-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f6574-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f6574-107">PR_CONVERSION_WITH_LOSS_PROHIBITED</span><span class="sxs-lookup"><span data-stu-id="f6574-107">PR_CONVERSION_WITH_LOSS_PROHIBITED</span></span>  <br/> |
|<span data-ttu-id="f6574-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f6574-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f6574-109">0x000D</span><span class="sxs-lookup"><span data-stu-id="f6574-109">0x000D</span></span>  <br/> |
|<span data-ttu-id="f6574-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f6574-110">Data type:</span></span>  <br/> |<span data-ttu-id="f6574-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="f6574-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="f6574-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f6574-112">Area:</span></span>  <br/> |<span data-ttu-id="f6574-113">常规配置</span><span class="sxs-lookup"><span data-stu-id="f6574-113">General configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f6574-114">备注</span><span class="sxs-lookup"><span data-stu-id="f6574-114">Remarks</span></span>

<span data-ttu-id="f6574-115">禁止的转换类型的一个示例是，从 Unicode 到单字节字符集 (两字节) "丢失"映射。</span><span class="sxs-lookup"><span data-stu-id="f6574-115">An example of the type of conversion being prohibited is the "lossy" mapping from Unicode (two bytes per character) to a single-byte character set.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f6574-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="f6574-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f6574-117">头文件</span><span class="sxs-lookup"><span data-stu-id="f6574-117">Header files</span></span>

<span data-ttu-id="f6574-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f6574-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="f6574-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f6574-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="f6574-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f6574-120">Mapitags.h</span></span>
  
> <span data-ttu-id="f6574-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f6574-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f6574-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6574-122">See also</span></span>



[<span data-ttu-id="f6574-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f6574-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f6574-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6574-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f6574-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f6574-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f6574-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f6574-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

