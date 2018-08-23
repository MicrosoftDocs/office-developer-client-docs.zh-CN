---
title: PidTagRemoteProgress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteProgress
api_type:
- COM
ms.assetid: 01cae79e-5b56-4cd4-83a6-f0956ff539fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e1f57fd95ff38ef102cd74b0035dbb6b553259c9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569349"
---
# <a name="pidtagremoteprogress-canonical-property"></a><span data-ttu-id="f8eb6-103">PidTagRemoteProgress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f8eb6-103">PidTagRemoteProgress Canonical Property</span></span>

  
  
<span data-ttu-id="f8eb6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8eb6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8eb6-105">此属性包含一个数字，指示远程传输的状态。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-105">This property contains a number that indicates the status of a remote transfer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f8eb6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f8eb6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f8eb6-107">PR_REMOTE_PROGRESS</span><span class="sxs-lookup"><span data-stu-id="f8eb6-107">PR_REMOTE_PROGRESS</span></span>  <br/> |
|<span data-ttu-id="f8eb6-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f8eb6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f8eb6-109">0x3E0B</span><span class="sxs-lookup"><span data-stu-id="f8eb6-109">0x3E0B</span></span>  <br/> |
|<span data-ttu-id="f8eb6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f8eb6-110">Data type:</span></span>  <br/> |<span data-ttu-id="f8eb6-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f8eb6-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f8eb6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f8eb6-112">Area:</span></span>  <br/> |<span data-ttu-id="f8eb6-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="f8eb6-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f8eb6-114">注解</span><span class="sxs-lookup"><span data-stu-id="f8eb6-114">Remarks</span></span>

<span data-ttu-id="f8eb6-115">如果没有传输正在进行，则此属性应设置为 1。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-115">If no transfer is in progress, this property should be set to 1.</span></span> <span data-ttu-id="f8eb6-116">如果正在传输，它应从 0 到 100 指示转接的完成百分比设置为值。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-116">If a transfer is in progress, it should be set to a value from 0 to 100 indicating the transfer's percent of completion.</span></span>
  
<span data-ttu-id="f8eb6-117">具有数值状态代码关联的文本显示**PR_REMOTE_PROGRESS_TEXT** ([PidTagRemoteProgressText](pidtagremoteprogresstext-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-117">The text associated with the numeric status code appears in the **PR_REMOTE_PROGRESS_TEXT** ([PidTagRemoteProgressText](pidtagremoteprogresstext-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="f8eb6-118">可以为此属性设置的以下标记：</span><span class="sxs-lookup"><span data-stu-id="f8eb6-118">The following flags can be set for this property:</span></span>
  
<span data-ttu-id="f8eb6-119">MSGSTATUS_REMOTE_DELETE</span><span class="sxs-lookup"><span data-stu-id="f8eb6-119">MSGSTATUS_REMOTE_DELETE</span></span>
  
> <span data-ttu-id="f8eb6-120">在传输邮件将被删除。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-120">The message transfer is deleted.</span></span>
    
<span data-ttu-id="f8eb6-121">MSGSTATUS_REMOTE_DOWNLOAD</span><span class="sxs-lookup"><span data-stu-id="f8eb6-121">MSGSTATUS_REMOTE_DOWNLOAD</span></span>
  
> <span data-ttu-id="f8eb6-122">邮件传输正在进行。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-122">The message transfer is in progress.</span></span>
    
## <a name="related-resources"></a><span data-ttu-id="f8eb6-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="f8eb6-123">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f8eb6-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f8eb6-124">Header files</span></span>

<span data-ttu-id="f8eb6-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f8eb6-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f8eb6-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="f8eb6-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f8eb6-127">Mapitags.h</span></span>
  
> <span data-ttu-id="f8eb6-128">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f8eb6-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f8eb6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8eb6-129">See also</span></span>



[<span data-ttu-id="f8eb6-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f8eb6-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f8eb6-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f8eb6-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f8eb6-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f8eb6-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f8eb6-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f8eb6-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

