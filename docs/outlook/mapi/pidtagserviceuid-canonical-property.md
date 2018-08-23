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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eabcaaf1db6149ef200e640f5af152758261581b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582249"
---
# <a name="pidtagserviceuid-canonical-property"></a><span data-ttu-id="1dc72-103">PidTagServiceUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="1dc72-103">PidTagServiceUid Canonical Property</span></span>

  
  
<span data-ttu-id="1dc72-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1dc72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1dc72-105">包含消息服务的[MAPIUID](mapiuid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="1dc72-105">Contains the [MAPIUID](mapiuid.md) structure for a message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1dc72-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1dc72-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1dc72-107">PR_SERVICE_UID</span><span class="sxs-lookup"><span data-stu-id="1dc72-107">PR_SERVICE_UID</span></span>  <br/> |
|<span data-ttu-id="1dc72-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1dc72-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1dc72-109">0x3D0C</span><span class="sxs-lookup"><span data-stu-id="1dc72-109">0x3D0C</span></span>  <br/> |
|<span data-ttu-id="1dc72-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1dc72-110">Data type:</span></span>  <br/> |<span data-ttu-id="1dc72-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1dc72-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1dc72-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1dc72-112">Area:</span></span>  <br/> |<span data-ttu-id="1dc72-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="1dc72-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1dc72-114">注解</span><span class="sxs-lookup"><span data-stu-id="1dc72-114">Remarks</span></span>

<span data-ttu-id="1dc72-115">此属性通过 MAPI 配置文件部分对象上计算。</span><span class="sxs-lookup"><span data-stu-id="1dc72-115">This property is computed by MAPI on profile section objects.</span></span> <span data-ttu-id="1dc72-116">MAPI 使用它组属于同一消息服务的所有提供商。</span><span class="sxs-lookup"><span data-stu-id="1dc72-116">MAPI uses it to group all the providers that belong to the same message service.</span></span> <span data-ttu-id="1dc72-117">此属性是作为大部分[IMsgServiceAdmin](imsgserviceadminiunknown.md)方法的参数提供的。</span><span class="sxs-lookup"><span data-stu-id="1dc72-117">This property is supplied as a parameter to most of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) methods.</span></span> <span data-ttu-id="1dc72-118">它必须 Mapisvc.inf 中不显示。</span><span class="sxs-lookup"><span data-stu-id="1dc72-118">It must not appear in Mapisvc.inf.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1dc72-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="1dc72-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1dc72-120">头文件</span><span class="sxs-lookup"><span data-stu-id="1dc72-120">Header files</span></span>

<span data-ttu-id="1dc72-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1dc72-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="1dc72-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1dc72-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="1dc72-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1dc72-123">Mapitags.h</span></span>
  
> <span data-ttu-id="1dc72-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1dc72-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1dc72-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dc72-125">See also</span></span>



[<span data-ttu-id="1dc72-126">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1dc72-126">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="1dc72-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1dc72-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1dc72-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1dc72-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1dc72-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1dc72-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1dc72-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1dc72-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

