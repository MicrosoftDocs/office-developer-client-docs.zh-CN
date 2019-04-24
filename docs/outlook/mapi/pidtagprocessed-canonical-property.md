---
title: PidTagProcessed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProcessed
api_type:
- COM
ms.assetid: 44884f60-7e36-45b2-9712-4f9821a0dc1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d84e9cb693cbe732295ee1891b4219450eb09ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351434"
---
# <a name="pidtagprocessed-canonical-property"></a><span data-ttu-id="c42b6-103">PidTagProcessed 规范属性</span><span class="sxs-lookup"><span data-stu-id="c42b6-103">PidTagProcessed Canonical Property</span></span>

  
  
<span data-ttu-id="c42b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c42b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c42b6-105">在处理会议请求后设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c42b6-105">Set to TRUE when the meeting request has been processed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c42b6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c42b6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c42b6-107">PR_PROCESSED</span><span class="sxs-lookup"><span data-stu-id="c42b6-107">PR_PROCESSED</span></span>  <br/> |
|<span data-ttu-id="c42b6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c42b6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c42b6-109">0x7D01</span><span class="sxs-lookup"><span data-stu-id="c42b6-109">0x7D01</span></span>  <br/> |
|<span data-ttu-id="c42b6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c42b6-110">Data type:</span></span>  <br/> |<span data-ttu-id="c42b6-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c42b6-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c42b6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c42b6-112">Area:</span></span>  <br/> |<span data-ttu-id="c42b6-113">日历</span><span class="sxs-lookup"><span data-stu-id="c42b6-113">Calendar</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c42b6-114">注解</span><span class="sxs-lookup"><span data-stu-id="c42b6-114">Remarks</span></span>

<span data-ttu-id="c42b6-115">此属性可确保只处理一次会议请求。</span><span class="sxs-lookup"><span data-stu-id="c42b6-115">This property ensures that meeting requests get processed once.</span></span> <span data-ttu-id="c42b6-116">请求的创建者应将此属性设置为 FALSE, 并且当请求位于日历中时, 收件人应将其设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c42b6-116">The creator of the request should set this property to FALSE and the receiver should set it to TRUE once the request is in the calendar.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c42b6-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="c42b6-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c42b6-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="c42b6-118">Protocol specifications</span></span>

<span data-ttu-id="c42b6-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c42b6-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c42b6-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c42b6-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c42b6-121">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c42b6-121">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c42b6-122">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c42b6-122">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="c42b6-123">[[毫秒-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c42b6-123">[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c42b6-124">指定允许用于联系人和个人通讯组列表对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c42b6-124">Specifies the properties and operations that are permissible for contact and personal distribution list objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c42b6-125">头文件</span><span class="sxs-lookup"><span data-stu-id="c42b6-125">Header files</span></span>

<span data-ttu-id="c42b6-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c42b6-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="c42b6-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c42b6-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="c42b6-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c42b6-128">Mapitags.h</span></span>
  
> <span data-ttu-id="c42b6-129">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c42b6-129">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c42b6-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c42b6-130">See also</span></span>



[<span data-ttu-id="c42b6-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c42b6-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c42b6-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c42b6-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c42b6-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c42b6-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c42b6-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c42b6-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

