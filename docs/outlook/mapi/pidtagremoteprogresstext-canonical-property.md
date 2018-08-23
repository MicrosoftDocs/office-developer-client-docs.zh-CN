---
title: PidTagRemoteProgressText 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemoteProgressText
api_type:
- COM
ms.assetid: b74d4350-4ad6-4c3f-8326-bd28537dfa0f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0a9d6bbe6807c2893c1bb208976dae9e695aa125
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592800"
---
# <a name="pidtagremoteprogresstext-canonical-property"></a><span data-ttu-id="2ae3f-103">PidTagRemoteProgressText 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ae3f-103">PidTagRemoteProgressText Canonical Property</span></span>

  
  
<span data-ttu-id="2ae3f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ae3f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ae3f-105">此属性包含一个字符串，指示远程传输的状态。</span><span class="sxs-lookup"><span data-stu-id="2ae3f-105">This property contains a string that indicates the status of a remote transfer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ae3f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2ae3f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ae3f-107">PR_REMOTE_PROGRESS_TEXT，PR_REMOTE_PROGRESS_TEXT_A，PR_REMOTE_PROGRESS_TEXT_W</span><span class="sxs-lookup"><span data-stu-id="2ae3f-107">PR_REMOTE_PROGRESS_TEXT, PR_REMOTE_PROGRESS_TEXT_A, PR_REMOTE_PROGRESS_TEXT_W</span></span>  <br/> |
|<span data-ttu-id="2ae3f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="2ae3f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2ae3f-109">0x3E0C</span><span class="sxs-lookup"><span data-stu-id="2ae3f-109">0x3E0C</span></span>  <br/> |
|<span data-ttu-id="2ae3f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ae3f-110">Data type:</span></span>  <br/> |<span data-ttu-id="2ae3f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2ae3f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2ae3f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2ae3f-112">Area:</span></span>  <br/> |<span data-ttu-id="2ae3f-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="2ae3f-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ae3f-114">注解</span><span class="sxs-lookup"><span data-stu-id="2ae3f-114">Remarks</span></span>

<span data-ttu-id="2ae3f-115">与此文本相关联的数字代码传递**PR_REMOTE_PROGRESS** ([PidTagRemoteProgress](pidtagremoteprogress-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="2ae3f-115">A numeric code associated with this text is passed in the **PR_REMOTE_PROGRESS** ([PidTagRemoteProgress](pidtagremoteprogress-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2ae3f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ae3f-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2ae3f-117">头文件</span><span class="sxs-lookup"><span data-stu-id="2ae3f-117">Header files</span></span>

<span data-ttu-id="2ae3f-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ae3f-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ae3f-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ae3f-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="2ae3f-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2ae3f-120">Mapitags.h</span></span>
  
> <span data-ttu-id="2ae3f-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2ae3f-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ae3f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae3f-122">See also</span></span>



[<span data-ttu-id="2ae3f-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ae3f-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ae3f-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ae3f-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ae3f-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ae3f-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ae3f-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ae3f-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

