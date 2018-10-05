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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 851441e419c17d8f5fef27c785ea4b829a4ae443
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385835"
---
# <a name="pidtagclientsubmittime-canonical-property"></a><span data-ttu-id="dd716-103">PidTagClientSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd716-103">PidTagClientSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="dd716-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd716-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd716-105">包含的日期和时间发件人提交一条消息。</span><span class="sxs-lookup"><span data-stu-id="dd716-105">Contains the date and time the message sender submitted a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dd716-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dd716-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dd716-107">期限</span><span class="sxs-lookup"><span data-stu-id="dd716-107">PR_CLIENT_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="dd716-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="dd716-108">Identifier:</span></span>  <br/> |<span data-ttu-id="dd716-109">0x0039</span><span class="sxs-lookup"><span data-stu-id="dd716-109">0x0039</span></span>  <br/> |
|<span data-ttu-id="dd716-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dd716-110">Data type:</span></span>  <br/> |<span data-ttu-id="dd716-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="dd716-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="dd716-112">区域：</span><span class="sxs-lookup"><span data-stu-id="dd716-112">Area:</span></span>  <br/> |<span data-ttu-id="dd716-113">消息时间</span><span class="sxs-lookup"><span data-stu-id="dd716-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dd716-114">说明</span><span class="sxs-lookup"><span data-stu-id="dd716-114">Remarks</span></span>

<span data-ttu-id="dd716-115">存储提供程序将**期限**设置为客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)的时间。</span><span class="sxs-lookup"><span data-stu-id="dd716-115">The store provider sets **PR_CLIENT_SUBMIT_TIME** to the time that the client application called [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="dd716-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="dd716-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dd716-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="dd716-117">Protocol specifications</span></span>

<span data-ttu-id="dd716-118">[[MS OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dd716-118">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dd716-119">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="dd716-119">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dd716-120">头文件</span><span class="sxs-lookup"><span data-stu-id="dd716-120">Header files</span></span>

<span data-ttu-id="dd716-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dd716-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="dd716-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dd716-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="dd716-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="dd716-123">Mapitags.h</span></span>
  
> <span data-ttu-id="dd716-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="dd716-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dd716-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd716-125">See also</span></span>



[<span data-ttu-id="dd716-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dd716-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dd716-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dd716-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dd716-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dd716-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dd716-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dd716-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

