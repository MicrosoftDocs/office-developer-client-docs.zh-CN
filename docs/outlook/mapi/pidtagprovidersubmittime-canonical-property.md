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
ms.openlocfilehash: c5e840250da7ba3b95150f2e83e1eb08b0c61ab5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409018"
---
# <a name="pidtagprovidersubmittime-canonical-property"></a><span data-ttu-id="d5944-103">PidTagProviderSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5944-103">PidTagProviderSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="d5944-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5944-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5944-105">包含传输提供程序将邮件传递到其基础邮件系统的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d5944-105">Contains the date and time a transport provider passed a message to its underlying messaging system.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d5944-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d5944-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d5944-107">PR_PROVIDER_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="d5944-107">PR_PROVIDER_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="d5944-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d5944-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d5944-109">0x0048</span><span class="sxs-lookup"><span data-stu-id="d5944-109">0x0048</span></span>  <br/> |
|<span data-ttu-id="d5944-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d5944-110">Data type:</span></span>  <br/> |<span data-ttu-id="d5944-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="d5944-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="d5944-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d5944-112">Area:</span></span>  <br/> |<span data-ttu-id="d5944-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="d5944-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5944-114">备注</span><span class="sxs-lookup"><span data-stu-id="d5944-114">Remarks</span></span>

<span data-ttu-id="d5944-115">此属性由传出传输提供程序在邮件发送时设置。</span><span class="sxs-lookup"><span data-stu-id="d5944-115">This property is set by the outgoing transport provider at the time a message is sent.</span></span>
  
<span data-ttu-id="d5944-116">此属性对应于每封邮件的 X.400 提交信封属性。</span><span class="sxs-lookup"><span data-stu-id="d5944-116">This property corresponds to an X.400 submission envelope per-message attribute.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d5944-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d5944-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="d5944-118">头文件</span><span class="sxs-lookup"><span data-stu-id="d5944-118">Header files</span></span>

<span data-ttu-id="d5944-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d5944-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="d5944-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d5944-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="d5944-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d5944-121">Mapitags.h</span></span>
  
> <span data-ttu-id="d5944-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d5944-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d5944-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5944-123">See also</span></span>



[<span data-ttu-id="d5944-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d5944-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d5944-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d5944-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d5944-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d5944-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d5944-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d5944-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

