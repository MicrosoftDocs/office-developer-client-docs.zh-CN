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
ms.openlocfilehash: d5c6e1dc30c3ee7862341bce204b4a78bd6d379b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426525"
---
# <a name="pidtagserviceuid-canonical-property"></a><span data-ttu-id="74f94-103">PidTagServiceUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="74f94-103">PidTagServiceUid Canonical Property</span></span>

  
  
<span data-ttu-id="74f94-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74f94-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74f94-105">包含 [邮件服务的 MAPIUID](mapiuid.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="74f94-105">Contains the [MAPIUID](mapiuid.md) structure for a message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="74f94-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="74f94-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="74f94-107">PR_SERVICE_UID</span><span class="sxs-lookup"><span data-stu-id="74f94-107">PR_SERVICE_UID</span></span>  <br/> |
|<span data-ttu-id="74f94-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="74f94-108">Identifier:</span></span>  <br/> |<span data-ttu-id="74f94-109">0x3D0C</span><span class="sxs-lookup"><span data-stu-id="74f94-109">0x3D0C</span></span>  <br/> |
|<span data-ttu-id="74f94-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="74f94-110">Data type:</span></span>  <br/> |<span data-ttu-id="74f94-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="74f94-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="74f94-112">区域：</span><span class="sxs-lookup"><span data-stu-id="74f94-112">Area:</span></span>  <br/> |<span data-ttu-id="74f94-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="74f94-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="74f94-114">备注</span><span class="sxs-lookup"><span data-stu-id="74f94-114">Remarks</span></span>

<span data-ttu-id="74f94-115">此属性由配置文件节对象的 MAPI 计算。</span><span class="sxs-lookup"><span data-stu-id="74f94-115">This property is computed by MAPI on profile section objects.</span></span> <span data-ttu-id="74f94-116">MAPI 使用它对属于同一邮件服务的所有提供程序进行分组。</span><span class="sxs-lookup"><span data-stu-id="74f94-116">MAPI uses it to group all the providers that belong to the same message service.</span></span> <span data-ttu-id="74f94-117">此属性作为参数提供给大多数 [IMsgServiceAdmin](imsgserviceadminiunknown.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="74f94-117">This property is supplied as a parameter to most of the [IMsgServiceAdmin](imsgserviceadminiunknown.md) methods.</span></span> <span data-ttu-id="74f94-118">它不得显示在 Mapisvc.inf 中。</span><span class="sxs-lookup"><span data-stu-id="74f94-118">It must not appear in Mapisvc.inf.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="74f94-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="74f94-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="74f94-120">头文件</span><span class="sxs-lookup"><span data-stu-id="74f94-120">Header files</span></span>

<span data-ttu-id="74f94-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="74f94-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="74f94-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="74f94-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="74f94-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="74f94-123">Mapitags.h</span></span>
  
> <span data-ttu-id="74f94-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="74f94-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74f94-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f94-125">See also</span></span>



[<span data-ttu-id="74f94-126">IMsgServiceAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="74f94-126">IMsgServiceAdmin : IUnknown</span></span>](imsgserviceadminiunknown.md)


[<span data-ttu-id="74f94-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="74f94-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="74f94-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="74f94-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="74f94-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="74f94-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="74f94-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="74f94-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

