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
ms.openlocfilehash: 7f55b85e21f007be7c1b9d42d42473e3a8d2becb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778230"
---
# <a name="pidtagresolvemethod-canonical-property"></a><span data-ttu-id="ea7c7-103">PidTagResolveMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="ea7c7-103">PidTagResolveMethod Canonical Property</span></span>

  
  
<span data-ttu-id="ea7c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ea7c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ea7c7-105">包含某个文件夹的冲突解决值。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-105">Contains a folder's conflict resolution value.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ea7c7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ea7c7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ea7c7-107">PR_RESOLVE_METHOD</span><span class="sxs-lookup"><span data-stu-id="ea7c7-107">PR_RESOLVE_METHOD</span></span>  <br/> |
|<span data-ttu-id="ea7c7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ea7c7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ea7c7-109">0x3FE7</span><span class="sxs-lookup"><span data-stu-id="ea7c7-109">0x3FE7</span></span>  <br/> |
|<span data-ttu-id="ea7c7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ea7c7-110">Data type:</span></span>  <br/> |<span data-ttu-id="ea7c7-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ea7c7-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ea7c7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ea7c7-112">Area:</span></span>  <br/> |<span data-ttu-id="ea7c7-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="ea7c7-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ea7c7-114">说明</span><span class="sxs-lookup"><span data-stu-id="ea7c7-114">Remarks</span></span>

<span data-ttu-id="ea7c7-115">此属性包含冲突解决消息的文件夹将指示如何解决冲突。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-115">This property on the folder containing the conflict resolution message will indicate how to resolve the conflict.</span></span> <span data-ttu-id="ea7c7-116">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-116">This property is not required.</span></span> <span data-ttu-id="ea7c7-117">但是，如果设置，则之外以下标志不必须存在：</span><span class="sxs-lookup"><span data-stu-id="ea7c7-117">However, if it is set, flags other than the following must not be present:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ea7c7-118">RESOLVE_METHOD_DEFAULT (0X00000000)</span><span class="sxs-lookup"><span data-stu-id="ea7c7-118">RESOLVE_METHOD_DEFAULT (0x00000000)</span></span>  <br/> |<span data-ttu-id="ea7c7-119">冲突解决应生成消息。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-119">Conflict resolve message should be generated.</span></span>  <br/> |
|<span data-ttu-id="ea7c7-120">RESOLVE_METHOD_LAST_WRITER_WINS (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="ea7c7-120">RESOLVE_METHOD_LAST_WRITER_WINS (0x00000001)</span></span>  <br/> |<span data-ttu-id="ea7c7-121">用当前应用的更改覆盖目标邮件。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-121">Overwrite target message with current changes being applied.</span></span>  <br/> |
|<span data-ttu-id="ea7c7-122">RESOLVE_NO_CONFLICT_NOTIFICATION (0X00000002:UC)</span><span class="sxs-lookup"><span data-stu-id="ea7c7-122">RESOLVE_NO_CONFLICT_NOTIFICATION (0x00000002)</span></span>  <br/> |<span data-ttu-id="ea7c7-123">时生成冲突解决公用文件夹中的消息，则不发送冲突通知消息。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-123">Do not send conflict notification message when generating conflict resolve message in public folder.</span></span>  <br/> |
   
<span data-ttu-id="ea7c7-124">客户端或服务器一定不会产生冲突解决消息关联邮件。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-124">A client or server must not generate a conflict resolve message for associated messages.</span></span> <span data-ttu-id="ea7c7-125">通过使用**RESOLVE_METHOD_LAST_WRITER_WINS**语义，必须解决这些消息。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-125">These messages must be resolved by using **RESOLVE_METHOD_LAST_WRITER_WINS** semantics.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ea7c7-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="ea7c7-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ea7c7-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="ea7c7-127">Protocol specifications</span></span>

<span data-ttu-id="ea7c7-128">[[MS OXCSYNC]](http://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ea7c7-128">[[MS-OXCSYNC]](http://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ea7c7-129">同步服务器和客户端之间的消息对象数据的句柄。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-129">Handles synchronizing messaging object data between a server and a client.</span></span>
    
<span data-ttu-id="ea7c7-130">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ea7c7-130">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ea7c7-131">定义所使用的基本的数据结构中远程操作。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-131">Defines the basic data structures that are used in remote operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ea7c7-132">头文件</span><span class="sxs-lookup"><span data-stu-id="ea7c7-132">Header files</span></span>

<span data-ttu-id="ea7c7-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ea7c7-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="ea7c7-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="ea7c7-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ea7c7-135">Mapitags.h</span></span>
  
> <span data-ttu-id="ea7c7-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ea7c7-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ea7c7-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea7c7-137">See also</span></span>



[<span data-ttu-id="ea7c7-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ea7c7-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ea7c7-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ea7c7-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ea7c7-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ea7c7-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ea7c7-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ea7c7-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

