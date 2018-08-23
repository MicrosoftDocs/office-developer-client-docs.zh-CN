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
ms.openlocfilehash: e08b56fcfea38bf65e8628acfa481716554e2c01
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571610"
---
# <a name="pidtagprovidersubmittime-canonical-property"></a><span data-ttu-id="31077-103">PidTagProviderSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="31077-103">PidTagProviderSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="31077-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="31077-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="31077-105">包含的日期和时间传输提供程序传递给其基础的消息系统的一条消息。</span><span class="sxs-lookup"><span data-stu-id="31077-105">Contains the date and time a transport provider passed a message to its underlying messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="31077-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="31077-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="31077-107">PR_PROVIDER_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="31077-107">PR_PROVIDER_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="31077-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="31077-108">Identifier:</span></span>  <br/> |<span data-ttu-id="31077-109">0x0048</span><span class="sxs-lookup"><span data-stu-id="31077-109">0x0048</span></span>  <br/> |
|<span data-ttu-id="31077-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="31077-110">Data type:</span></span>  <br/> |<span data-ttu-id="31077-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="31077-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="31077-112">区域：</span><span class="sxs-lookup"><span data-stu-id="31077-112">Area:</span></span>  <br/> |<span data-ttu-id="31077-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="31077-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="31077-114">注解</span><span class="sxs-lookup"><span data-stu-id="31077-114">Remarks</span></span>

<span data-ttu-id="31077-115">发送邮件时，此属性将由传出传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="31077-115">This property is set by the outgoing transport provider at the time a message is sent.</span></span>
  
<span data-ttu-id="31077-116">此属性对应于 X.400 提交信封每封邮件属性。</span><span class="sxs-lookup"><span data-stu-id="31077-116">This property corresponds to an X.400 submission envelope per-message attribute.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="31077-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="31077-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="31077-118">头文件</span><span class="sxs-lookup"><span data-stu-id="31077-118">Header files</span></span>

<span data-ttu-id="31077-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="31077-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="31077-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="31077-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="31077-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="31077-121">Mapitags.h</span></span>
  
> <span data-ttu-id="31077-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="31077-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="31077-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31077-123">See also</span></span>



[<span data-ttu-id="31077-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="31077-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="31077-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="31077-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="31077-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="31077-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="31077-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="31077-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

