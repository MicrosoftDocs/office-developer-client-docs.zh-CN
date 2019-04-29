---
title: PidTagTransportKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransportKey
api_type:
- COM
ms.assetid: 131211b3-e6f9-4dd4-b6d9-b65361bff775
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 05db434ddabbd5f60fccdfeb1a2df8b3fcd0d96a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405546"
---
# <a name="pidtagtransportkey-canonical-property"></a><span data-ttu-id="22b48-103">PidTagTransportKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="22b48-103">PidTagTransportKey Canonical Property</span></span>

  
  
<span data-ttu-id="22b48-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22b48-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22b48-105">包含 MAPI 后台处理程序用来通过传出传输提供程序跟踪出站邮件进度的值。</span><span class="sxs-lookup"><span data-stu-id="22b48-105">Contains a value used by the MAPI spooler to track the progress of an outbound message through the outgoing transport providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="22b48-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="22b48-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="22b48-107">PR_TRANSPORT_KEY</span><span class="sxs-lookup"><span data-stu-id="22b48-107">PR_TRANSPORT_KEY</span></span>  <br/> |
|<span data-ttu-id="22b48-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="22b48-108">Identifier:</span></span>  <br/> |<span data-ttu-id="22b48-109">0x0E16</span><span class="sxs-lookup"><span data-stu-id="22b48-109">0x0E16</span></span>  <br/> |
|<span data-ttu-id="22b48-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="22b48-110">Data type:</span></span>  <br/> |<span data-ttu-id="22b48-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="22b48-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="22b48-112">区域：</span><span class="sxs-lookup"><span data-stu-id="22b48-112">Area:</span></span>  <br/> |<span data-ttu-id="22b48-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="22b48-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="22b48-114">说明</span><span class="sxs-lookup"><span data-stu-id="22b48-114">Remarks</span></span>

<span data-ttu-id="22b48-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="22b48-115">Do not use this property.</span></span> <span data-ttu-id="22b48-116">它保留供 MAPI 使用。</span><span class="sxs-lookup"><span data-stu-id="22b48-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="22b48-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="22b48-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="22b48-118">头文件</span><span class="sxs-lookup"><span data-stu-id="22b48-118">Header files</span></span>

<span data-ttu-id="22b48-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="22b48-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="22b48-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="22b48-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="22b48-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="22b48-121">Mapitags.h</span></span>
  
> <span data-ttu-id="22b48-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="22b48-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="22b48-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22b48-123">See also</span></span>



[<span data-ttu-id="22b48-124">PidTagTransportProviders 规范属性</span><span class="sxs-lookup"><span data-stu-id="22b48-124">PidTagTransportProviders Canonical Property</span></span>](pidtagtransportproviders-canonical-property.md)


[<span data-ttu-id="22b48-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="22b48-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="22b48-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="22b48-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="22b48-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="22b48-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="22b48-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="22b48-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

