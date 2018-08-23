---
title: PidNameExchangeJunkEmailMoveStamp 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameExchangeJunkEmailMoveStamp
api_type:
- COM
ms.assetid: 7a52f46c-371c-46d0-8d66-e154482e8269
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1312f590dfc0e8388495351dd4870fcf8b9e22f0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591364"
---
# <a name="pidnameexchangejunkemailmovestamp-canonical-property"></a><span data-ttu-id="9cbb6-103">PidNameExchangeJunkEmailMoveStamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cbb6-103">PidNameExchangeJunkEmailMoveStamp Canonical Property</span></span>

  
  
<span data-ttu-id="9cbb6-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cbb6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9cbb6-105">包含持久化的消息值，该值指示的消息因为已处理或安全，邮件不应处理垃圾邮件筛选器。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-105">Contains the persisted message value that indicates that the message should not be processed by a spam filter because the message was either already processed or is safe.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9cbb6-106">友好名称：</span><span class="sxs-lookup"><span data-stu-id="9cbb6-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="9cbb6-107">无</span><span class="sxs-lookup"><span data-stu-id="9cbb6-107">None</span></span>  <br/> |
|<span data-ttu-id="9cbb6-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="9cbb6-108">Property set:</span></span>  <br/> |<span data-ttu-id="9cbb6-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="9cbb6-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="9cbb6-110">属性名称：</span><span class="sxs-lookup"><span data-stu-id="9cbb6-110">Property name:</span></span>  <br/> |http://schemas.microsoft.com/exchange/junkemailmovestamp  <br/> |
|<span data-ttu-id="9cbb6-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9cbb6-111">Data type:</span></span>  <br/> |<span data-ttu-id="9cbb6-112">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="9cbb6-112">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="9cbb6-113">区域：</span><span class="sxs-lookup"><span data-stu-id="9cbb6-113">Area:</span></span>  <br/> |<span data-ttu-id="9cbb6-114">安全邮件</span><span class="sxs-lookup"><span data-stu-id="9cbb6-114">Secure messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9cbb6-115">注解</span><span class="sxs-lookup"><span data-stu-id="9cbb6-115">Remarks</span></span>

<span data-ttu-id="9cbb6-116">此属性标记上每封邮件的垃圾邮件规则移动或否则受信任的内容。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-116">This property is stamped on every message that is moved by the Junk E-Mail Rule or is otherwise trusted content.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9cbb6-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9cbb6-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9cbb6-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="9cbb6-118">Protocol specifications</span></span>

<span data-ttu-id="9cbb6-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cbb6-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9cbb6-120">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-120">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9cbb6-121">[[MS OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cbb6-121">[[MS-OXCSPAM]](http://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9cbb6-122">允许处理的允许/阻止列表，并确定的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-122">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="9cbb6-123">[[MS OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cbb6-123">[[MS-OXORSS]](http://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9cbb6-124">指定的属性和表示 RSS 项目的操作。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-124">Specifies the properties and operations that represent RSS items.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9cbb6-125">头文件</span><span class="sxs-lookup"><span data-stu-id="9cbb6-125">Header files</span></span>

<span data-ttu-id="9cbb6-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9cbb6-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="9cbb6-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9cbb6-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9cbb6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cbb6-128">See also</span></span>



[<span data-ttu-id="9cbb6-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9cbb6-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9cbb6-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9cbb6-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9cbb6-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9cbb6-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9cbb6-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9cbb6-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

