---
title: PidTagBodyCrc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBodyCrc
api_type:
- HeaderDef
ms.assetid: 6efe9dc3-e988-4042-ab02-2863b5e0f294
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 66a150cf3f83465840aa0e79a9ef921b1534f814
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777398"
---
# <a name="pidtagbodycrc-canonical-property"></a><span data-ttu-id="e276e-103">PidTagBodyCrc 规范属性</span><span class="sxs-lookup"><span data-stu-id="e276e-103">PidTagBodyCrc Canonical Property</span></span>

  
  
<span data-ttu-id="e276e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e276e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e276e-105">包含消息文本在一个循环冗余检查 (CRC) 值。</span><span class="sxs-lookup"><span data-stu-id="e276e-105">Contains a cyclic redundancy check (CRC) value on the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e276e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e276e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e276e-107">PR_BODY_CRC</span><span class="sxs-lookup"><span data-stu-id="e276e-107">PR_BODY_CRC</span></span>  <br/> |
|<span data-ttu-id="e276e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e276e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e276e-109">0x0E1C</span><span class="sxs-lookup"><span data-stu-id="e276e-109">0x0E1C</span></span>  <br/> |
|<span data-ttu-id="e276e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e276e-110">Data type:</span></span>  <br/> |<span data-ttu-id="e276e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e276e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e276e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e276e-112">Area:</span></span>  <br/> |<span data-ttu-id="e276e-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="e276e-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e276e-114">说明</span><span class="sxs-lookup"><span data-stu-id="e276e-114">Remarks</span></span>

<span data-ttu-id="e276e-115">消息存储库可以使用任何 CRC 算法生成 PT_LONG 值。</span><span class="sxs-lookup"><span data-stu-id="e276e-115">The message store can use any CRC algorithm that generates a PT_LONG value.</span></span> <span data-ttu-id="e276e-116">它必须时**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性已设置第一次，只要随后已修改计算此属性作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="e276e-116">It must compute this property as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method when the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property has been set for the first time and whenever it has been subsequently modified.</span></span>
  
<span data-ttu-id="e276e-117">客户端应用程序使用**PR_BODY_CRC**帮助比较**PR_BODY**属性或其变量中包含的消息文本字符串。</span><span class="sxs-lookup"><span data-stu-id="e276e-117">A client application uses **PR_BODY_CRC** to aid in comparing message text strings contained in **PR_BODY** properties or their variants.</span></span> <span data-ttu-id="e276e-118">使用此属性，客户端可以快速、 方便地检测何时更改消息文本。</span><span class="sxs-lookup"><span data-stu-id="e276e-118">Using this property, the client can quickly and easily detect when the message text has changed.</span></span> <span data-ttu-id="e276e-119">它可以使用而不是从消息存储中获取**PR_BODY**并将其与本地版本进行比较**PR_BODY_CRC**实现显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="e276e-119">It can realize significant performance gains by using **PR_BODY_CRC** instead of obtaining **PR_BODY** from the message store and comparing it with a local version.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e276e-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="e276e-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="e276e-121">头文件</span><span class="sxs-lookup"><span data-stu-id="e276e-121">Header files</span></span>

<span data-ttu-id="e276e-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e276e-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="e276e-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e276e-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="e276e-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e276e-124">Mapitags.h</span></span>
  
> <span data-ttu-id="e276e-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e276e-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e276e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e276e-126">See also</span></span>



[<span data-ttu-id="e276e-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e276e-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e276e-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e276e-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e276e-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e276e-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e276e-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e276e-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

