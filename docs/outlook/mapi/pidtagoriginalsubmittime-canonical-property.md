---
title: PidTagOriginalSubmitTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSubmitTime
api_type:
- COM
ms.assetid: 2e027c0c-2370-437a-ad98-2bbb5e41e525
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 43d0387f1c25c5ac86168caaddddd9fb9171c827
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777969"
---
# <a name="pidtagoriginalsubmittime-canonical-property"></a><span data-ttu-id="bb70a-103">PidTagOriginalSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb70a-103">PidTagOriginalSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="bb70a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bb70a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bb70a-105">包含的原始的提交日期和时间报告中的邮件。</span><span class="sxs-lookup"><span data-stu-id="bb70a-105">Contains the original submission date and time of the message in the report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bb70a-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="bb70a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb70a-107">PR_ORIGINAL_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="bb70a-107">PR_ORIGINAL_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="bb70a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bb70a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bb70a-109">0x004E</span><span class="sxs-lookup"><span data-stu-id="bb70a-109">0x004E</span></span>  <br/> |
|<span data-ttu-id="bb70a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb70a-110">Data type:</span></span>  <br/> |<span data-ttu-id="bb70a-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="bb70a-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="bb70a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bb70a-112">Area:</span></span>  <br/> |<span data-ttu-id="bb70a-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="bb70a-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb70a-114">备注</span><span class="sxs-lookup"><span data-stu-id="bb70a-114">Remarks</span></span>

<span data-ttu-id="bb70a-115">在首次提交一条消息，客户端应用程序应将此属性设置为**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="bb70a-115">At first submission of a message, a client application should set this property to the value of the **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property.</span></span> <span data-ttu-id="bb70a-116">转发邮件时不会更改。</span><span class="sxs-lookup"><span data-stu-id="bb70a-116">It is not changed when the message is forwarded.</span></span> <span data-ttu-id="bb70a-117">这仅用于报表中使用。</span><span class="sxs-lookup"><span data-stu-id="bb70a-117">This is used in reports only.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bb70a-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb70a-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb70a-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb70a-119">Protocol specifications</span></span>

<span data-ttu-id="bb70a-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb70a-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb70a-121">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="bb70a-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="bb70a-122">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb70a-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb70a-123">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="bb70a-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bb70a-124">头文件</span><span class="sxs-lookup"><span data-stu-id="bb70a-124">Header files</span></span>

<span data-ttu-id="bb70a-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb70a-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb70a-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb70a-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="bb70a-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bb70a-127">Mapitags.h</span></span>
  
> <span data-ttu-id="bb70a-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bb70a-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb70a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb70a-129">See also</span></span>



[<span data-ttu-id="bb70a-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb70a-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb70a-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb70a-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb70a-132">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb70a-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb70a-133">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb70a-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

