---
title: PidTagExpiryTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExpiryTime
api_type:
- HeaderDef
ms.assetid: 6e4d4ee9-c6b1-4987-b02e-684c2af3d21c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 21e052545c9c5e68bf1bc2f8c1ead054163f3b8d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566143"
---
# <a name="pidtagexpirytime-canonical-property"></a><span data-ttu-id="57b68-103">PidTagExpiryTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="57b68-103">PidTagExpiryTime Canonical Property</span></span>

  
  
<span data-ttu-id="57b68-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57b68-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57b68-105">包含的日期和时间在邮件系统时使一条消息的内容失效。</span><span class="sxs-lookup"><span data-stu-id="57b68-105">Contains the date and time when the messaging system can invalidate the content of a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57b68-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="57b68-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="57b68-107">PR_EXPIRY_TIME</span><span class="sxs-lookup"><span data-stu-id="57b68-107">PR_EXPIRY_TIME</span></span>  <br/> |
|<span data-ttu-id="57b68-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="57b68-108">Identifier:</span></span>  <br/> |<span data-ttu-id="57b68-109">0x0015</span><span class="sxs-lookup"><span data-stu-id="57b68-109">0x0015</span></span>  <br/> |
|<span data-ttu-id="57b68-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="57b68-110">Data type:</span></span>  <br/> |<span data-ttu-id="57b68-111">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="57b68-111">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="57b68-112">区域：</span><span class="sxs-lookup"><span data-stu-id="57b68-112">Area:</span></span>  <br/> |<span data-ttu-id="57b68-113">MAPI 信封</span><span class="sxs-lookup"><span data-stu-id="57b68-113">MAPI envelope</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="57b68-114">注解</span><span class="sxs-lookup"><span data-stu-id="57b68-114">Remarks</span></span>

<span data-ttu-id="57b68-115">此属性用于直接中处理的消息系统传递人际邮件。</span><span class="sxs-lookup"><span data-stu-id="57b68-115">This property is used to direct the messaging system in handling delivered interpersonal messages.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="57b68-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="57b68-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="57b68-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="57b68-117">Protocol specifications</span></span>

<span data-ttu-id="57b68-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57b68-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57b68-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="57b68-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="57b68-120">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="57b68-120">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="57b68-121">指定的属性和电子邮件中允许的操作。</span><span class="sxs-lookup"><span data-stu-id="57b68-121">Specifies the properties and operations that are permissible on email messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="57b68-122">头文件</span><span class="sxs-lookup"><span data-stu-id="57b68-122">Header files</span></span>

<span data-ttu-id="57b68-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="57b68-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="57b68-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="57b68-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="57b68-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="57b68-125">Mapitags.h</span></span>
  
> <span data-ttu-id="57b68-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="57b68-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="57b68-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57b68-127">See also</span></span>



[<span data-ttu-id="57b68-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="57b68-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="57b68-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="57b68-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="57b68-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="57b68-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="57b68-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="57b68-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

