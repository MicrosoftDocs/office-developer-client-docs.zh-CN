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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326605"
---
# <a name="pidtagtransportkey-canonical-property"></a><span data-ttu-id="ca7b0-103">PidTagTransportKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca7b0-103">PidTagTransportKey Canonical Property</span></span>

  
  
<span data-ttu-id="ca7b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca7b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca7b0-105">包含 MAPI 后台处理程序用来通过传出传输提供程序跟踪出站邮件进度的值。</span><span class="sxs-lookup"><span data-stu-id="ca7b0-105">Contains a value used by the MAPI spooler to track the progress of an outbound message through the outgoing transport providers.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca7b0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ca7b0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca7b0-107">PR_TRANSPORT_KEY</span><span class="sxs-lookup"><span data-stu-id="ca7b0-107">PR_TRANSPORT_KEY</span></span>  <br/> |
|<span data-ttu-id="ca7b0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ca7b0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca7b0-109">0x0E16</span><span class="sxs-lookup"><span data-stu-id="ca7b0-109">0x0E16</span></span>  <br/> |
|<span data-ttu-id="ca7b0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ca7b0-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca7b0-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ca7b0-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ca7b0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ca7b0-112">Area:</span></span>  <br/> |<span data-ttu-id="ca7b0-113">MAPI 非传输</span><span class="sxs-lookup"><span data-stu-id="ca7b0-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca7b0-114">注解</span><span class="sxs-lookup"><span data-stu-id="ca7b0-114">Remarks</span></span>

<span data-ttu-id="ca7b0-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="ca7b0-115">Do not use this property.</span></span> <span data-ttu-id="ca7b0-116">它保留供 MAPI 使用。</span><span class="sxs-lookup"><span data-stu-id="ca7b0-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ca7b0-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ca7b0-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ca7b0-118">头文件</span><span class="sxs-lookup"><span data-stu-id="ca7b0-118">Header files</span></span>

<span data-ttu-id="ca7b0-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ca7b0-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca7b0-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ca7b0-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca7b0-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ca7b0-121">Mapitags.h</span></span>
  
> <span data-ttu-id="ca7b0-122">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ca7b0-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca7b0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca7b0-123">See also</span></span>



[<span data-ttu-id="ca7b0-124">PidTagTransportProviders 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca7b0-124">PidTagTransportProviders Canonical Property</span></span>](pidtagtransportproviders-canonical-property.md)


[<span data-ttu-id="ca7b0-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ca7b0-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca7b0-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca7b0-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca7b0-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ca7b0-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca7b0-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ca7b0-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

