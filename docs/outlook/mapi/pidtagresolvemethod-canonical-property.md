---
title: PidTagResolveMethod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResolveMethod
api_type:
- COM
ms.assetid: 30d23c19-e0da-4511-9361-761153259216
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14bb31ae9aebbb6441948b5756b426508107c9f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331400"
---
# <a name="pidtagresolvemethod-canonical-property"></a><span data-ttu-id="0f377-103">PidTagResolveMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f377-103">PidTagResolveMethod Canonical Property</span></span>

  
  
<span data-ttu-id="0f377-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0f377-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0f377-105">包含文件夹的冲突解决值。</span><span class="sxs-lookup"><span data-stu-id="0f377-105">Contains a folder's conflict resolution value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0f377-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0f377-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0f377-107">PR_RESOLVE_METHOD</span><span class="sxs-lookup"><span data-stu-id="0f377-107">PR_RESOLVE_METHOD</span></span>  <br/> |
|<span data-ttu-id="0f377-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0f377-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0f377-109">0x3FE7</span><span class="sxs-lookup"><span data-stu-id="0f377-109">0x3FE7</span></span>  <br/> |
|<span data-ttu-id="0f377-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0f377-110">Data type:</span></span>  <br/> |<span data-ttu-id="0f377-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0f377-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0f377-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0f377-112">Area:</span></span>  <br/> |<span data-ttu-id="0f377-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="0f377-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0f377-114">注解</span><span class="sxs-lookup"><span data-stu-id="0f377-114">Remarks</span></span>

<span data-ttu-id="0f377-115">包含冲突解决邮件的文件夹上的此属性将指示如何解决冲突。</span><span class="sxs-lookup"><span data-stu-id="0f377-115">This property on the folder containing the conflict resolution message will indicate how to resolve the conflict.</span></span> <span data-ttu-id="0f377-116">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="0f377-116">This property is not required.</span></span> <span data-ttu-id="0f377-117">但是, 如果设置了, 则不能有以下标志:</span><span class="sxs-lookup"><span data-stu-id="0f377-117">However, if it is set, flags other than the following must not be present:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0f377-118">RESOLVE_METHOD_DEFAULT (0x00000000)</span><span class="sxs-lookup"><span data-stu-id="0f377-118">RESOLVE_METHOD_DEFAULT (0x00000000)</span></span>  <br/> |<span data-ttu-id="0f377-119">应生成冲突解决消息。</span><span class="sxs-lookup"><span data-stu-id="0f377-119">Conflict resolve message should be generated.</span></span>  <br/> |
|<span data-ttu-id="0f377-120">RESOLVE_METHOD_LAST_WRITER_WINS (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="0f377-120">RESOLVE_METHOD_LAST_WRITER_WINS (0x00000001)</span></span>  <br/> |<span data-ttu-id="0f377-121">使用当前正在应用的更改覆盖目标邮件。</span><span class="sxs-lookup"><span data-stu-id="0f377-121">Overwrite target message with current changes being applied.</span></span>  <br/> |
|<span data-ttu-id="0f377-122">RESOLVE_NO_CONFLICT_NOTIFICATION (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="0f377-122">RESOLVE_NO_CONFLICT_NOTIFICATION (0x00000002)</span></span>  <br/> |<span data-ttu-id="0f377-123">在公用文件夹中生成冲突解决邮件时不发送冲突通知消息。</span><span class="sxs-lookup"><span data-stu-id="0f377-123">Do not send conflict notification message when generating conflict resolve message in public folder.</span></span>  <br/> |
   
<span data-ttu-id="0f377-124">客户端或服务器不能为关联的邮件生成冲突解决消息。</span><span class="sxs-lookup"><span data-stu-id="0f377-124">A client or server must not generate a conflict resolve message for associated messages.</span></span> <span data-ttu-id="0f377-125">必须使用**RESOLVE_METHOD_LAST_WRITER_WINS**语义解决这些邮件。</span><span class="sxs-lookup"><span data-stu-id="0f377-125">These messages must be resolved by using **RESOLVE_METHOD_LAST_WRITER_WINS** semantics.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0f377-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="0f377-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0f377-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="0f377-127">Protocol specifications</span></span>

<span data-ttu-id="0f377-128">[[毫秒-OXCSYNC]](https://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0f377-128">[[MS-OXCSYNC]](https://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0f377-129">处理服务器和客户端之间的同步邮件对象数据。</span><span class="sxs-lookup"><span data-stu-id="0f377-129">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="0f377-130">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0f377-130">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0f377-131">定义在远程操作中使用的基本数据结构。</span><span class="sxs-lookup"><span data-stu-id="0f377-131">Defines the basic data structures that are used in remote operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0f377-132">头文件</span><span class="sxs-lookup"><span data-stu-id="0f377-132">Header files</span></span>

<span data-ttu-id="0f377-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0f377-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="0f377-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0f377-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="0f377-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0f377-135">Mapitags.h</span></span>
  
> <span data-ttu-id="0f377-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0f377-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0f377-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f377-137">See also</span></span>



[<span data-ttu-id="0f377-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0f377-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0f377-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0f377-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0f377-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0f377-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0f377-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0f377-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

