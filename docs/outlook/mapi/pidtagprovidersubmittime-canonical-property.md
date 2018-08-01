---
title: PidTagProviderSubmitTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderSubmitTime
api_type:
- COM
ms.assetid: 9e5161d9-fefe-4a12-b7f7-5600f1d2e95b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 162451d000c0b3da42c8fbef5f64459bc5ae23b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778092"
---
# <a name="pidtagprovidersubmittime-canonical-property"></a><span data-ttu-id="dea50-103">PidTagProviderSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="dea50-103">PidTagProviderSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="dea50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dea50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dea50-105">包含的日期和时间传输提供程序传递给其基础的消息系统的一条消息。</span><span class="sxs-lookup"><span data-stu-id="dea50-105">Contains the date and time a transport provider passed a message to its underlying messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dea50-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dea50-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dea50-107">PR_PROVIDER_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="dea50-107">PR_PROVIDER_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="dea50-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="dea50-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dea50-109">0x0048</span><span class="sxs-lookup"><span data-stu-id="dea50-109">0x0048</span></span>  <br/> |
|<span data-ttu-id="dea50-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dea50-110">Data type:</span></span>  <br/> |<span data-ttu-id="dea50-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="dea50-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="dea50-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dea50-112">Area:</span></span>  <br/> |<span data-ttu-id="dea50-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="dea50-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dea50-114">说明</span><span class="sxs-lookup"><span data-stu-id="dea50-114">Remarks</span></span>

<span data-ttu-id="dea50-115">发送邮件时，此属性将由传出传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="dea50-115">This property is set by the outgoing transport provider at the time a message is sent.</span></span>
  
<span data-ttu-id="dea50-116">此属性对应于 X.400 提交信封每封邮件属性。</span><span class="sxs-lookup"><span data-stu-id="dea50-116">This property corresponds to an X.400 submission envelope per-message attribute.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="dea50-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="dea50-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="dea50-118">头文件</span><span class="sxs-lookup"><span data-stu-id="dea50-118">Header files</span></span>

<span data-ttu-id="dea50-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dea50-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="dea50-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dea50-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="dea50-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dea50-121">Mapitags.h</span></span>
  
> <span data-ttu-id="dea50-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dea50-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dea50-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dea50-123">See also</span></span>



[<span data-ttu-id="dea50-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dea50-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dea50-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dea50-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dea50-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dea50-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dea50-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dea50-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

