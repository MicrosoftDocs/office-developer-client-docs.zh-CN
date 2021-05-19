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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424222"
---
# <a name="pidtagremotevalidateok-canonical-property"></a><span data-ttu-id="156c8-103">PidTagRemoteValidateOk 规范属性</span><span class="sxs-lookup"><span data-stu-id="156c8-103">PidTagRemoteValidateOk Canonical Property</span></span>

  
  
<span data-ttu-id="156c8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="156c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="156c8-105">如果允许远程查看器调用 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法，则此属性包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="156c8-105">This property contains TRUE if the remote viewer is allowed to call the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="156c8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="156c8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="156c8-107">PR_REMOTE_VALIDATE_OK</span><span class="sxs-lookup"><span data-stu-id="156c8-107">PR_REMOTE_VALIDATE_OK</span></span>  <br/> |
|<span data-ttu-id="156c8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="156c8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="156c8-109">0x3E0D</span><span class="sxs-lookup"><span data-stu-id="156c8-109">0x3E0D</span></span>  <br/> |
|<span data-ttu-id="156c8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="156c8-110">Data type:</span></span>  <br/> |<span data-ttu-id="156c8-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="156c8-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="156c8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="156c8-112">Area:</span></span>  <br/> |<span data-ttu-id="156c8-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="156c8-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="156c8-114">备注</span><span class="sxs-lookup"><span data-stu-id="156c8-114">Remarks</span></span>

<span data-ttu-id="156c8-115">此属性显示在状态表中，并提供对传输性能的一些控制。</span><span class="sxs-lookup"><span data-stu-id="156c8-115">This property appears in the status table and offers some control over transport performance.</span></span> <span data-ttu-id="156c8-116">它可视为将远程查看器引导到空闲的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="156c8-116">It can be considered as another way of directing the remote viewer to idle.</span></span> <span data-ttu-id="156c8-117">当设置为 TRUE 时，远程查看器可以视需要经常调用 **IMAPIStatus：：ValidateState。**</span><span class="sxs-lookup"><span data-stu-id="156c8-117">When it is set to TRUE, the remote viewer can call **IMAPIStatus::ValidateState** as often as desired.</span></span> <span data-ttu-id="156c8-118">FALSE 值指示远程查看器不能再进行更多调用。</span><span class="sxs-lookup"><span data-stu-id="156c8-118">A value of FALSE indicates that the remote viewer cannot make any more calls.</span></span> 
  
<span data-ttu-id="156c8-119">传输提供程序通常通过将值设置为 FALSE 来动态设置此属性，以在传输提供程序具有足够的处理量时禁用其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="156c8-119">The transport provider usually sets this property dynamically, by setting the value to FALSE to disable additional calls when the transport provider has a sufficient amount of processing to perform.</span></span> <span data-ttu-id="156c8-120">传输提供程序完成后，它会将值设置成 TRUE，以允许客户端应用程序进行进一步 **IMAPIStatus：：ValidateState** 调用。</span><span class="sxs-lookup"><span data-stu-id="156c8-120">When the transport provider is done, it then sets the value to TRUE to allow the client application to make further **IMAPIStatus::ValidateState** calls.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="156c8-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="156c8-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="156c8-122">头文件</span><span class="sxs-lookup"><span data-stu-id="156c8-122">Header files</span></span>

<span data-ttu-id="156c8-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="156c8-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="156c8-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="156c8-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="156c8-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="156c8-125">Mapitags.h</span></span>
  
> <span data-ttu-id="156c8-126">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="156c8-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="156c8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="156c8-127">See also</span></span>



[<span data-ttu-id="156c8-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="156c8-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="156c8-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="156c8-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="156c8-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="156c8-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="156c8-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="156c8-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

