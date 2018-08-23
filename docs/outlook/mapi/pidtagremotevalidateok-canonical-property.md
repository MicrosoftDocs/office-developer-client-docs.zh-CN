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
ms.openlocfilehash: 9b06ebbe8cb162d77d60cfffa866438567c84c27
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576832"
---
# <a name="pidtagremotevalidateok-canonical-property"></a><span data-ttu-id="ad10d-103">PidTagRemoteValidateOk 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad10d-103">PidTagRemoteValidateOk Canonical Property</span></span>

  
  
<span data-ttu-id="ad10d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad10d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad10d-105">此属性包含 TRUE 如果允许远程查看器调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ad10d-105">This property contains TRUE if the remote viewer is allowed to call the [IMAPIStatus::ValidateState](imapistatus-validatestate.md) method.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad10d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ad10d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ad10d-107">PR_REMOTE_VALIDATE_OK</span><span class="sxs-lookup"><span data-stu-id="ad10d-107">PR_REMOTE_VALIDATE_OK</span></span>  <br/> |
|<span data-ttu-id="ad10d-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ad10d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ad10d-109">0x3E0D</span><span class="sxs-lookup"><span data-stu-id="ad10d-109">0x3E0D</span></span>  <br/> |
|<span data-ttu-id="ad10d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ad10d-110">Data type:</span></span>  <br/> |<span data-ttu-id="ad10d-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ad10d-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ad10d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ad10d-112">Area:</span></span>  <br/> |<span data-ttu-id="ad10d-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="ad10d-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ad10d-114">注解</span><span class="sxs-lookup"><span data-stu-id="ad10d-114">Remarks</span></span>

<span data-ttu-id="ad10d-115">此属性将状态表中显示，并提供一些控制传输性能。</span><span class="sxs-lookup"><span data-stu-id="ad10d-115">This property appears in the status table and offers some control over transport performance.</span></span> <span data-ttu-id="ad10d-116">它可以将其视为另一种用于为空闲远程查看器。</span><span class="sxs-lookup"><span data-stu-id="ad10d-116">It can be considered as another way of directing the remote viewer to idle.</span></span> <span data-ttu-id="ad10d-117">当设置为 TRUE 时，远程查看器可以根据需要通常调用**IMAPIStatus::ValidateState** 。</span><span class="sxs-lookup"><span data-stu-id="ad10d-117">When it is set to TRUE, the remote viewer can call **IMAPIStatus::ValidateState** as often as desired.</span></span> <span data-ttu-id="ad10d-118">值为 FALSE 指示远程查看器无法进行任何其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad10d-118">A value of FALSE indicates that the remote viewer cannot make any more calls.</span></span> 
  
<span data-ttu-id="ad10d-119">传输提供程序通常将该属性设置动态，值设置为 FALSE 可禁用其他呼叫时的传输提供程序具有足够的执行的处理。</span><span class="sxs-lookup"><span data-stu-id="ad10d-119">The transport provider usually sets this property dynamically, by setting the value to FALSE to disable additional calls when the transport provider has a sufficient amount of processing to perform.</span></span> <span data-ttu-id="ad10d-120">完成传输提供程序后，它然后将值设置为 TRUE 以允许客户端应用程序进行进一步**IMAPIStatus::ValidateState**呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad10d-120">When the transport provider is done, it then sets the value to TRUE to allow the client application to make further **IMAPIStatus::ValidateState** calls.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ad10d-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="ad10d-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ad10d-122">头文件</span><span class="sxs-lookup"><span data-stu-id="ad10d-122">Header files</span></span>

<span data-ttu-id="ad10d-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ad10d-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="ad10d-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ad10d-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="ad10d-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ad10d-125">Mapitags.h</span></span>
  
> <span data-ttu-id="ad10d-126">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ad10d-126">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad10d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad10d-127">See also</span></span>



[<span data-ttu-id="ad10d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ad10d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ad10d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad10d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ad10d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ad10d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ad10d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ad10d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

