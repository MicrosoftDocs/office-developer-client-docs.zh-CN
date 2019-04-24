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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345715"
---
# <a name="pidtagclientsubmittime-canonical-property"></a><span data-ttu-id="9af90-103">PidTagClientSubmitTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="9af90-103">PidTagClientSubmitTime Canonical Property</span></span>

  
  
<span data-ttu-id="9af90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9af90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9af90-105">包含邮件发件人提交邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9af90-105">Contains the date and time the message sender submitted a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9af90-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9af90-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9af90-107">PR_CLIENT_SUBMIT_TIME</span><span class="sxs-lookup"><span data-stu-id="9af90-107">PR_CLIENT_SUBMIT_TIME</span></span>  <br/> |
|<span data-ttu-id="9af90-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="9af90-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9af90-109">0x0039</span><span class="sxs-lookup"><span data-stu-id="9af90-109">0x0039</span></span>  <br/> |
|<span data-ttu-id="9af90-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9af90-110">Data type:</span></span>  <br/> |<span data-ttu-id="9af90-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="9af90-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="9af90-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9af90-112">Area:</span></span>  <br/> |<span data-ttu-id="9af90-113">邮件时间</span><span class="sxs-lookup"><span data-stu-id="9af90-113">Message time</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9af90-114">注解</span><span class="sxs-lookup"><span data-stu-id="9af90-114">Remarks</span></span>

<span data-ttu-id="9af90-115">存储提供程序将**PR_CLIENT_SUBMIT_TIME**设置为客户端应用程序调用[IMessage:: SubmitMessage](imessage-submitmessage.md)的时间。</span><span class="sxs-lookup"><span data-stu-id="9af90-115">The store provider sets **PR_CLIENT_SUBMIT_TIME** to the time that the client application called [IMessage::SubmitMessage](imessage-submitmessage.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="9af90-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="9af90-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9af90-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="9af90-117">Protocol specifications</span></span>

<span data-ttu-id="9af90-118">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9af90-118">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9af90-119">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="9af90-119">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9af90-120">头文件</span><span class="sxs-lookup"><span data-stu-id="9af90-120">Header files</span></span>

<span data-ttu-id="9af90-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="9af90-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="9af90-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9af90-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="9af90-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="9af90-123">Mapitags.h</span></span>
  
> <span data-ttu-id="9af90-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9af90-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9af90-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9af90-125">See also</span></span>



[<span data-ttu-id="9af90-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9af90-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9af90-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9af90-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9af90-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9af90-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9af90-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9af90-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

