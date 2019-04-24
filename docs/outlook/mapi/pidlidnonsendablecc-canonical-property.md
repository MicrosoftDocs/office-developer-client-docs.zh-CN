---
title: PidLidNonSendableCc 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendableCc
api_type:
- COM
ms.assetid: 170afe1f-1223-4689-825c-d21ab14b213b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d9f166b0d1e180fdb087fbf602e6841c3fdac3dc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319654"
---
# <a name="pidlidnonsendablecc-canonical-property"></a><span data-ttu-id="2e2bb-103">PidLidNonSendableCc 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e2bb-103">PidLidNonSendableCc Canonical Property</span></span>

  
  
<span data-ttu-id="2e2bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2e2bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2e2bb-105">包含所有 unsendable 与会者的列表, 这些与会者也是可选的与会者。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-105">Contains a list of all the unsendable attendees who are also optional attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e2bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2e2bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2e2bb-107">dispidNonSendableCC</span><span class="sxs-lookup"><span data-stu-id="2e2bb-107">dispidNonSendableCC</span></span>  <br/> |
|<span data-ttu-id="2e2bb-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="2e2bb-108">Property set:</span></span>  <br/> |<span data-ttu-id="2e2bb-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2e2bb-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2e2bb-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="2e2bb-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2e2bb-111">0x00008537</span><span class="sxs-lookup"><span data-stu-id="2e2bb-111">0x00008537</span></span>  <br/> |
|<span data-ttu-id="2e2bb-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2e2bb-112">Data type:</span></span>  <br/> |<span data-ttu-id="2e2bb-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2e2bb-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2e2bb-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2e2bb-114">Area:</span></span>  <br/> |<span data-ttu-id="2e2bb-115">会议</span><span class="sxs-lookup"><span data-stu-id="2e2bb-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2e2bb-116">注解</span><span class="sxs-lookup"><span data-stu-id="2e2bb-116">Remarks</span></span>

<span data-ttu-id="2e2bb-117">每个与会者的值都是与会者通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-117">The value for each attendee is the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of the attendee's Address Book.</span></span> <span data-ttu-id="2e2bb-118">单独的条目必须用分号分隔, 后跟空格。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="2e2bb-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2e2bb-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="2e2bb-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2e2bb-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="2e2bb-121">Protocol specifications</span></span>

<span data-ttu-id="2e2bb-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e2bb-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e2bb-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2e2bb-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e2bb-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e2bb-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
<span data-ttu-id="2e2bb-126">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2e2bb-126">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2e2bb-127">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-127">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2e2bb-128">头文件</span><span class="sxs-lookup"><span data-stu-id="2e2bb-128">Header files</span></span>

<span data-ttu-id="2e2bb-129">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2e2bb-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="2e2bb-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2e2bb-130">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2e2bb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e2bb-131">See also</span></span>



[<span data-ttu-id="2e2bb-132">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2e2bb-132">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2e2bb-133">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2e2bb-133">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2e2bb-134">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2e2bb-134">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2e2bb-135">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2e2bb-135">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

