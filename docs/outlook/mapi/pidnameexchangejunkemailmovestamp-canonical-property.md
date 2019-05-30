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
ms.openlocfilehash: 098261cd71631e4816d22272e1b1bef1d5932a94
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540943"
---
# <a name="pidnameexchangejunkemailmovestamp-canonical-property"></a><span data-ttu-id="ef616-103">PidNameExchangeJunkEmailMoveStamp 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef616-103">PidNameExchangeJunkEmailMoveStamp Canonical Property</span></span>

  
  
<span data-ttu-id="ef616-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef616-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef616-105">包含持久的消息值, 该值指示由于邮件已处理或安全, 垃圾邮件筛选器不应处理邮件。</span><span class="sxs-lookup"><span data-stu-id="ef616-105">Contains the persisted message value that indicates that the message should not be processed by a spam filter because the message was either already processed or is safe.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef616-106">友好名称:</span><span class="sxs-lookup"><span data-stu-id="ef616-106">Friendly names:</span></span>  <br/> |<span data-ttu-id="ef616-107">无</span><span class="sxs-lookup"><span data-stu-id="ef616-107">None</span></span>  <br/> |
|<span data-ttu-id="ef616-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="ef616-108">Property set:</span></span>  <br/> |<span data-ttu-id="ef616-109">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="ef616-109">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="ef616-110">属性名称:</span><span class="sxs-lookup"><span data-stu-id="ef616-110">Property name:</span></span>  <br/> |http://schemas.microsoft.com/exchange/junkemailmovestamp  <br/> |
|<span data-ttu-id="ef616-111">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ef616-111">Data type:</span></span>  <br/> |<span data-ttu-id="ef616-112">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="ef616-112">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="ef616-113">区域：</span><span class="sxs-lookup"><span data-stu-id="ef616-113">Area:</span></span>  <br/> |<span data-ttu-id="ef616-114">安全邮件</span><span class="sxs-lookup"><span data-stu-id="ef616-114">Secure messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ef616-115">备注</span><span class="sxs-lookup"><span data-stu-id="ef616-115">Remarks</span></span>

<span data-ttu-id="ef616-116">此属性在垃圾邮件规则移动的每封邮件上标记, 或以其他方式受信任的内容。</span><span class="sxs-lookup"><span data-stu-id="ef616-116">This property is stamped on every message that is moved by the Junk E-Mail Rule or is otherwise trusted content.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ef616-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ef616-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ef616-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="ef616-118">Protocol specifications</span></span>

<span data-ttu-id="ef616-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef616-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef616-120">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="ef616-120">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ef616-121">[[毫秒-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef616-121">[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef616-122">启用对允许/阻止列表的处理以及确定垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="ef616-122">Enables the handling of allow/block lists and the determination of junk email messages.</span></span>
    
<span data-ttu-id="ef616-123">[[毫秒-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef616-123">[[MS-OXORSS]](https://msdn.microsoft.com/library/53bc9634-0040-4b5a-aecd-29781d826009%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef616-124">指定表示 RSS 项目的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ef616-124">Specifies the properties and operations that represent RSS items.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ef616-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ef616-125">Header files</span></span>

<span data-ttu-id="ef616-126">Mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ef616-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ef616-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ef616-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ef616-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef616-128">See also</span></span>



[<span data-ttu-id="ef616-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ef616-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ef616-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef616-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ef616-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ef616-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ef616-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ef616-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

