---
title: PidTagServiceUid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceUid
api_type:
- COM
ms.assetid: 9d99a3b6-d0b4-4e8a-8f08-f46fdeb6b3e7
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 304efc3f4ea903f9ed0e9fcf95c7100fa6ebfc95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778422"
---
# <a name="pidtagserviceuid-canonical-property"></a><span data-ttu-id="76543-103">PidTagServiceUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="76543-103">PidTagServiceUid Canonical Property</span></span>

  
  
<span data-ttu-id="76543-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="76543-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="76543-105">包含消息服务的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="76543-105">Contains the [MAPIUID](mapiuid.md) structure for a message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76543-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="76543-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="76543-107">PR_SERVICE_UID</span><span class="sxs-lookup"><span data-stu-id="76543-107">PR_SERVICE_UID</span></span>  <br/> |
|<span data-ttu-id="76543-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="76543-108">Identifier:</span></span>  <br/> |<span data-ttu-id="76543-109">0x3D0C</span><span class="sxs-lookup"><span data-stu-id="76543-109">0x3D0C</span></span>  <br/> |
|<span data-ttu-id="76543-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="76543-110">Data type:</span></span>  <br/> |<span data-ttu-id="76543-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="76543-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="76543-112">区域：</span><span class="sxs-lookup"><span data-stu-id="76543-112">Area:</span></span>  <br/> |<span data-ttu-id="76543-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="76543-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="76543-114">备注</span><span class="sxs-lookup"><span data-stu-id="76543-114">Remarks</span></span>

<span data-ttu-id="76543-115">此属性通过 MAPI 配置文件部分对象上计算。</span><span class="sxs-lookup"><span data-stu-id="76543-115">This property is computed by MAPI on profile section objects.</span></span> <span data-ttu-id="76543-116">MAPI 使用它组属于同一消息服务的所有提供商。</span><span class="sxs-lookup"><span data-stu-id="76543-116">MAPI uses it to group all the providers that belong to the same message service.</span></span> <span data-ttu-id="76543-117">此属性是作为大部分[IMsgServiceAdmin](imsgserviceadminiunknown.md)方法的参数提供的。</span><span class="sxs-lookup"><span data-stu-id="76543-117">This property is supplied as a parameter to most of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) methods.</span></span> <span data-ttu-id="76543-118">它必须 Mapisvc.inf 中不显示。</span><span class="sxs-lookup"><span data-stu-id="76543-118">It must not appear in Mapisvc.inf.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="76543-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="76543-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="76543-120">头文件</span><span class="sxs-lookup"><span data-stu-id="76543-120">Header files</span></span>

<span data-ttu-id="76543-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="76543-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="76543-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="76543-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="76543-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="76543-123">Mapitags.h</span></span>
  
> <span data-ttu-id="76543-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="76543-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="76543-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76543-125">See also</span></span>



[<span data-ttu-id="76543-126">IMsgServiceAdmin: IUnknown</span><span class="sxs-lookup"><span data-stu-id="76543-126">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="76543-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="76543-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="76543-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="76543-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="76543-129">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="76543-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="76543-130">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="76543-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

