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
ms.openlocfilehash: b2a7a415f97af6aee4b9aa62b4349d2c40bfb55c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417011"
---
# <a name="pidtagremoteprogresstext-canonical-property"></a><span data-ttu-id="5f7ec-103">PidTagRemoteProgressText 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f7ec-103">PidTagRemoteProgressText Canonical Property</span></span>

  
  
<span data-ttu-id="5f7ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f7ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f7ec-105">此属性包含一个指示远程传输的状态的字符串。</span><span class="sxs-lookup"><span data-stu-id="5f7ec-105">This property contains a string that indicates the status of a remote transfer.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5f7ec-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5f7ec-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5f7ec-107">PR_REMOTE_PROGRESS_TEXT、PR_REMOTE_PROGRESS_TEXT_A、PR_REMOTE_PROGRESS_TEXT_W</span><span class="sxs-lookup"><span data-stu-id="5f7ec-107">PR_REMOTE_PROGRESS_TEXT, PR_REMOTE_PROGRESS_TEXT_A, PR_REMOTE_PROGRESS_TEXT_W</span></span>  <br/> |
|<span data-ttu-id="5f7ec-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5f7ec-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5f7ec-109">0x3E0C</span><span class="sxs-lookup"><span data-stu-id="5f7ec-109">0x3E0C</span></span>  <br/> |
|<span data-ttu-id="5f7ec-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5f7ec-110">Data type:</span></span>  <br/> |<span data-ttu-id="5f7ec-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5f7ec-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="5f7ec-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5f7ec-112">Area:</span></span>  <br/> |<span data-ttu-id="5f7ec-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="5f7ec-113">MAPI Status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5f7ec-114">说明</span><span class="sxs-lookup"><span data-stu-id="5f7ec-114">Remarks</span></span>

<span data-ttu-id="5f7ec-115">与此文本关联的数字代码在**PR_REMOTE_PROGRESS** ([PidTagRemoteProgress](pidtagremoteprogress-canonical-property.md)) 属性中传递。</span><span class="sxs-lookup"><span data-stu-id="5f7ec-115">A numeric code associated with this text is passed in the **PR_REMOTE_PROGRESS** ([PidTagRemoteProgress](pidtagremoteprogress-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5f7ec-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5f7ec-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5f7ec-117">头文件</span><span class="sxs-lookup"><span data-stu-id="5f7ec-117">Header files</span></span>

<span data-ttu-id="5f7ec-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5f7ec-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="5f7ec-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5f7ec-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="5f7ec-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5f7ec-120">Mapitags.h</span></span>
  
> <span data-ttu-id="5f7ec-121">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5f7ec-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f7ec-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f7ec-122">See also</span></span>



[<span data-ttu-id="5f7ec-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5f7ec-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5f7ec-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f7ec-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5f7ec-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5f7ec-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5f7ec-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5f7ec-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

