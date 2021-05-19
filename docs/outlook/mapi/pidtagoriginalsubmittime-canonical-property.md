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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 07aea33f54a29d497646b62f1f8bd96a383cbd7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341046"
---
# <a name="pidtagoriginalsubmittime-canonical-property"></a><span data-ttu-id="9eb51-103">PidTagOriginalSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="9eb51-103">PidTagOriginalSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="9eb51-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9eb51-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9eb51-105">包含报告中邮件的原始提交日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9eb51-105">Contains the original submission date and time of the message in the report.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9eb51-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9eb51-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9eb51-107">PR_ORIGINAL_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="9eb51-107">PR_ORIGINAL_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="9eb51-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9eb51-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9eb51-109">0x004E</span><span class="sxs-lookup"><span data-stu-id="9eb51-109">0x004E</span></span>  <br/> |
|<span data-ttu-id="9eb51-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9eb51-110">Data type:</span></span>  <br/> |<span data-ttu-id="9eb51-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="9eb51-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="9eb51-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9eb51-112">Area:</span></span>  <br/> |<span data-ttu-id="9eb51-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="9eb51-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9eb51-114">备注</span><span class="sxs-lookup"><span data-stu-id="9eb51-114">Remarks</span></span>

<span data-ttu-id="9eb51-115">首次提交邮件时，客户端应用程序应该将此属性设置为 PR_CLIENT_SUBMIT_TIME ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性的值。 </span><span class="sxs-lookup"><span data-stu-id="9eb51-115">At first submission of a message, a client application should set this property to the value of the **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property.</span></span> <span data-ttu-id="9eb51-116">转发邮件时不会更改。</span><span class="sxs-lookup"><span data-stu-id="9eb51-116">It is not changed when the message is forwarded.</span></span> <span data-ttu-id="9eb51-117">这仅在报告中使用。</span><span class="sxs-lookup"><span data-stu-id="9eb51-117">This is used in reports only.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9eb51-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="9eb51-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9eb51-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="9eb51-119">Protocol specifications</span></span>

<span data-ttu-id="9eb51-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9eb51-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9eb51-121">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="9eb51-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9eb51-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9eb51-122">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9eb51-123">指定允许对电子邮件对象执行的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="9eb51-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9eb51-124">头文件</span><span class="sxs-lookup"><span data-stu-id="9eb51-124">Header files</span></span>

<span data-ttu-id="9eb51-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9eb51-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="9eb51-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9eb51-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="9eb51-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9eb51-127">Mapitags.h</span></span>
  
> <span data-ttu-id="9eb51-128">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9eb51-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9eb51-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eb51-129">See also</span></span>



[<span data-ttu-id="9eb51-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9eb51-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9eb51-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9eb51-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9eb51-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9eb51-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9eb51-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9eb51-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

