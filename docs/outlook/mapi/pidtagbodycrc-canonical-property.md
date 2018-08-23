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
ms.openlocfilehash: 55da942e59c619dd384bef58349aa3a00d4a6d8c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571470"
---
# <a name="pidtagbodycrc-canonical-property"></a><span data-ttu-id="74f2f-103">PidTagBodyCrc 规范属性</span><span class="sxs-lookup"><span data-stu-id="74f2f-103">PidTagBodyCrc Canonical Property</span></span>

  
  
<span data-ttu-id="74f2f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74f2f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74f2f-105">包含消息文本在一个循环冗余检查 (CRC) 值。</span><span class="sxs-lookup"><span data-stu-id="74f2f-105">Contains a cyclic redundancy check (CRC) value on the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="74f2f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="74f2f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="74f2f-107">PR_BODY_CRC</span><span class="sxs-lookup"><span data-stu-id="74f2f-107">PR_BODY_CRC</span></span>  <br/> |
|<span data-ttu-id="74f2f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="74f2f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="74f2f-109">0x0E1C</span><span class="sxs-lookup"><span data-stu-id="74f2f-109">0x0E1C</span></span>  <br/> |
|<span data-ttu-id="74f2f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="74f2f-110">Data type:</span></span>  <br/> |<span data-ttu-id="74f2f-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="74f2f-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="74f2f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="74f2f-112">Area:</span></span>  <br/> |<span data-ttu-id="74f2f-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="74f2f-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="74f2f-114">注解</span><span class="sxs-lookup"><span data-stu-id="74f2f-114">Remarks</span></span>

<span data-ttu-id="74f2f-115">消息存储库可以使用任何 CRC 算法生成 PT_LONG 值。</span><span class="sxs-lookup"><span data-stu-id="74f2f-115">The message store can use any CRC algorithm that generates a PT_LONG value.</span></span> <span data-ttu-id="74f2f-116">它必须时**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性已设置第一次，只要随后已修改计算此属性作为[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的一部分。</span><span class="sxs-lookup"><span data-stu-id="74f2f-116">It must compute this property as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method when the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property has been set for the first time and whenever it has been subsequently modified.</span></span>
  
<span data-ttu-id="74f2f-117">客户端应用程序使用**PR_BODY_CRC**帮助比较**PR_BODY**属性或其变量中包含的消息文本字符串。</span><span class="sxs-lookup"><span data-stu-id="74f2f-117">A client application uses **PR_BODY_CRC** to aid in comparing message text strings contained in **PR_BODY** properties or their variants.</span></span> <span data-ttu-id="74f2f-118">使用此属性，客户端可以快速、 方便地检测何时更改消息文本。</span><span class="sxs-lookup"><span data-stu-id="74f2f-118">Using this property, the client can quickly and easily detect when the message text has changed.</span></span> <span data-ttu-id="74f2f-119">它可以使用而不是从消息存储中获取**PR_BODY**并将其与本地版本进行比较**PR_BODY_CRC**实现显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="74f2f-119">It can realize significant performance gains by using **PR_BODY_CRC** instead of obtaining **PR_BODY** from the message store and comparing it with a local version.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="74f2f-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="74f2f-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="74f2f-121">头文件</span><span class="sxs-lookup"><span data-stu-id="74f2f-121">Header files</span></span>

<span data-ttu-id="74f2f-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="74f2f-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="74f2f-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="74f2f-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="74f2f-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="74f2f-124">Mapitags.h</span></span>
  
> <span data-ttu-id="74f2f-125">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="74f2f-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74f2f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f2f-126">See also</span></span>



[<span data-ttu-id="74f2f-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="74f2f-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="74f2f-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="74f2f-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="74f2f-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="74f2f-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="74f2f-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="74f2f-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

