---
title: PidTagRemoteValidateOk 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteValidateOk
api_type:
- COM
ms.assetid: e336d2ec-57cb-4d08-bd6e-330ef7d9939e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b5c9e5bb2aa915d4b76d9998baaf504e7929b78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355613"
---
# <a name="pidtagremotevalidateok-canonical-property"></a><span data-ttu-id="844da-103">PidTagRemoteValidateOk 规范属性</span><span class="sxs-lookup"><span data-stu-id="844da-103">PidTagRemoteValidateOk Canonical Property</span></span>

  
  
<span data-ttu-id="844da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="844da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="844da-105">如果允许远程查看器调用[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法, 则此属性包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="844da-105">This property contains TRUE if the remote viewer is allowed to call the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="844da-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="844da-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="844da-107">PR_REMOTE_VALIDATE_OK</span><span class="sxs-lookup"><span data-stu-id="844da-107">PR_REMOTE_VALIDATE_OK</span></span>  <br/> |
|<span data-ttu-id="844da-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="844da-108">Identifier:</span></span>  <br/> |<span data-ttu-id="844da-109">0x3E0D</span><span class="sxs-lookup"><span data-stu-id="844da-109">0x3E0D</span></span>  <br/> |
|<span data-ttu-id="844da-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="844da-110">Data type:</span></span>  <br/> |<span data-ttu-id="844da-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="844da-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="844da-112">区域：</span><span class="sxs-lookup"><span data-stu-id="844da-112">Area:</span></span>  <br/> |<span data-ttu-id="844da-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="844da-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="844da-114">注解</span><span class="sxs-lookup"><span data-stu-id="844da-114">Remarks</span></span>

<span data-ttu-id="844da-115">此属性将显示在状态表中, 并提供对传输性能的一些控制。</span><span class="sxs-lookup"><span data-stu-id="844da-115">This property appears in the status table and offers some control over transport performance.</span></span> <span data-ttu-id="844da-116">可将其视为将远程查看器定向为空闲的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="844da-116">It can be considered as another way of directing the remote viewer to idle.</span></span> <span data-ttu-id="844da-117">当它设置为 TRUE 时, 远程查看器可以按需要的频率调用**IMAPIStatus:: ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="844da-117">When it is set to TRUE, the remote viewer can call **IMAPIStatus::ValidateState** as often as desired.</span></span> <span data-ttu-id="844da-118">如果值为 FALSE, 则表示远程查看器不能进行任何调用。</span><span class="sxs-lookup"><span data-stu-id="844da-118">A value of FALSE indicates that the remote viewer cannot make any more calls.</span></span> 
  
<span data-ttu-id="844da-119">传输提供程序通常会将此属性设置为 FALSE, 以便在传输提供程序有足够的处理要执行的大量处理时, 将该值设置为 FALSE, 以禁用其他调用。</span><span class="sxs-lookup"><span data-stu-id="844da-119">The transport provider usually sets this property dynamically, by setting the value to FALSE to disable additional calls when the transport provider has a sufficient amount of processing to perform.</span></span> <span data-ttu-id="844da-120">在传输提供程序完成后, 它会将值设置为 TRUE, 以允许客户端应用程序进一步**IMAPIStatus:: ValidateState**调用。</span><span class="sxs-lookup"><span data-stu-id="844da-120">When the transport provider is done, it then sets the value to TRUE to allow the client application to make further **IMAPIStatus::ValidateState** calls.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="844da-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="844da-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="844da-122">头文件</span><span class="sxs-lookup"><span data-stu-id="844da-122">Header files</span></span>

<span data-ttu-id="844da-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="844da-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="844da-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="844da-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="844da-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="844da-125">Mapitags.h</span></span>
  
> <span data-ttu-id="844da-126">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="844da-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="844da-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="844da-127">See also</span></span>



[<span data-ttu-id="844da-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="844da-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="844da-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="844da-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="844da-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="844da-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="844da-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="844da-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

