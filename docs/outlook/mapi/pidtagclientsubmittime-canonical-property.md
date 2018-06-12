---
title: PidTagClientSubmitTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagClientSubmitTime
api_type:
- HeaderDef
ms.assetid: d46e1063-6421-410d-a445-7477fea42089
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: ccf4a6054ecc89e280f2f5cbc4c72b2a8a829055
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777410"
---
# <a name="pidtagclientsubmittime-canonical-property"></a><span data-ttu-id="ad84f-103">PidTagClientSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad84f-103">PidTagClientSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="ad84f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ad84f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ad84f-105">包含的日期和时间发件人提交一条消息。</span><span class="sxs-lookup"><span data-stu-id="ad84f-105">Contains the date and time the message sender submitted a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad84f-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ad84f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ad84f-107">期限</span><span class="sxs-lookup"><span data-stu-id="ad84f-107">PR_CLIENT_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="ad84f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ad84f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ad84f-109">0x0039</span><span class="sxs-lookup"><span data-stu-id="ad84f-109">0x0039</span></span>  <br/> |
|<span data-ttu-id="ad84f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ad84f-110">Data type:</span></span>  <br/> |<span data-ttu-id="ad84f-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="ad84f-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="ad84f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ad84f-112">Area:</span></span>  <br/> |<span data-ttu-id="ad84f-113">消息时间</span><span class="sxs-lookup"><span data-stu-id="ad84f-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ad84f-114">备注</span><span class="sxs-lookup"><span data-stu-id="ad84f-114">Remarks</span></span>

<span data-ttu-id="ad84f-115">存储提供程序将**期限**设置为客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)的时间。</span><span class="sxs-lookup"><span data-stu-id="ad84f-115">The store provider sets **PR_CLIENT_SUBMIT_TIME** to the time that the client application called [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ad84f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="ad84f-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ad84f-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="ad84f-117">Protocol specifications</span></span>

<span data-ttu-id="ad84f-118">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ad84f-118">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ad84f-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="ad84f-119">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ad84f-120">头文件</span><span class="sxs-lookup"><span data-stu-id="ad84f-120">Header files</span></span>

<span data-ttu-id="ad84f-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ad84f-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="ad84f-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ad84f-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="ad84f-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ad84f-123">Mapitags.h</span></span>
  
> <span data-ttu-id="ad84f-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ad84f-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad84f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad84f-125">See also</span></span>



[<span data-ttu-id="ad84f-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ad84f-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ad84f-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ad84f-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ad84f-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ad84f-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ad84f-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ad84f-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

