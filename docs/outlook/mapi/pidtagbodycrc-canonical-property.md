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
ms.openlocfilehash: 416486c3b06c485a1fa6525b54c37a6e0d23f56c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415178"
---
# <a name="pidtagbodycrc-canonical-property"></a><span data-ttu-id="2ed0b-103">PidTagBodyCrc 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ed0b-103">PidTagBodyCrc Canonical Property</span></span>

  
  
<span data-ttu-id="2ed0b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ed0b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ed0b-105">包含对邮件文本 (CRC) 循环冗余检查。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-105">Contains a cyclic redundancy check (CRC) value on the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ed0b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2ed0b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ed0b-107">PR_BODY_CRC</span><span class="sxs-lookup"><span data-stu-id="2ed0b-107">PR_BODY_CRC</span></span>  <br/> |
|<span data-ttu-id="2ed0b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2ed0b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2ed0b-109">0x0E1C</span><span class="sxs-lookup"><span data-stu-id="2ed0b-109">0x0E1C</span></span>  <br/> |
|<span data-ttu-id="2ed0b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ed0b-110">Data type:</span></span>  <br/> |<span data-ttu-id="2ed0b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2ed0b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2ed0b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2ed0b-112">Area:</span></span>  <br/> |<span data-ttu-id="2ed0b-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="2ed0b-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ed0b-114">备注</span><span class="sxs-lookup"><span data-stu-id="2ed0b-114">Remarks</span></span>

<span data-ttu-id="2ed0b-115">邮件存储可以使用生成值的任何 CRC PT_LONG值。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-115">The message store can use any CRC algorithm that generates a PT_LONG value.</span></span> <span data-ttu-id="2ed0b-116">它必须在首次设置 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性时以及以后对其进行修改时，在 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法中计算此属性。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-116">It must compute this property as part of the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method when the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property has been set for the first time and whenever it has been subsequently modified.</span></span>
  
<span data-ttu-id="2ed0b-117">客户端应用程序使用 **PR_BODY_CRC** 帮助比较包含在属性或变量PR_BODY中的邮件文本字符串。 </span><span class="sxs-lookup"><span data-stu-id="2ed0b-117">A client application uses **PR_BODY_CRC** to aid in comparing message text strings contained in **PR_BODY** properties or their variants.</span></span> <span data-ttu-id="2ed0b-118">使用此属性，客户端可以快速且轻松地检测邮件文本何时发生更改。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-118">Using this property, the client can quickly and easily detect when the message text has changed.</span></span> <span data-ttu-id="2ed0b-119">通过使用 PR_BODY_CRC而不是从邮件存储PR_BODY它和本地版本进行比较，可以实现显著的性能提升。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-119">It can realize significant performance gains by using **PR_BODY_CRC** instead of obtaining **PR_BODY** from the message store and comparing it with a local version.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2ed0b-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ed0b-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2ed0b-121">头文件</span><span class="sxs-lookup"><span data-stu-id="2ed0b-121">Header files</span></span>

<span data-ttu-id="2ed0b-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ed0b-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ed0b-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="2ed0b-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2ed0b-124">Mapitags.h</span></span>
  
> <span data-ttu-id="2ed0b-125">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2ed0b-125">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ed0b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ed0b-126">See also</span></span>



[<span data-ttu-id="2ed0b-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ed0b-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ed0b-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ed0b-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ed0b-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ed0b-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ed0b-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ed0b-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

