---
title: PidLidNonSendableTo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendableTo
api_type:
- COM
ms.assetid: 90e14969-652b-422a-9b0a-ee99e58bc8d5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cc510cb9a4a79f977cb6c9721921833441df23c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345514"
---
# <a name="pidlidnonsendableto-canonical-property"></a><span data-ttu-id="68bf9-103">PidLidNonSendableTo 规范属性</span><span class="sxs-lookup"><span data-stu-id="68bf9-103">PidLidNonSendableTo Canonical Property</span></span>

  
  
<span data-ttu-id="68bf9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68bf9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68bf9-105">包含同时也是必需与会者的所有 unsendable 与会者的列表。</span><span class="sxs-lookup"><span data-stu-id="68bf9-105">Contains a list of all the unsendable attendees who are also required attendees.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="68bf9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="68bf9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="68bf9-107">dispidNonSendableTo</span><span class="sxs-lookup"><span data-stu-id="68bf9-107">dispidNonSendableTo</span></span>  <br/> |
|<span data-ttu-id="68bf9-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="68bf9-108">Property set:</span></span>  <br/> |<span data-ttu-id="68bf9-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="68bf9-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="68bf9-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="68bf9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="68bf9-111">0x00008536</span><span class="sxs-lookup"><span data-stu-id="68bf9-111">0x00008536</span></span>  <br/> |
|<span data-ttu-id="68bf9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="68bf9-112">Data type:</span></span>  <br/> |<span data-ttu-id="68bf9-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="68bf9-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="68bf9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="68bf9-114">Area:</span></span>  <br/> |<span data-ttu-id="68bf9-115">会议</span><span class="sxs-lookup"><span data-stu-id="68bf9-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="68bf9-116">注解</span><span class="sxs-lookup"><span data-stu-id="68bf9-116">Remarks</span></span>

<span data-ttu-id="68bf9-117">每个与会者的值都是与会者通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="68bf9-117">The value for each attendee is the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of the attendee's Address Book.</span></span> <span data-ttu-id="68bf9-118">单独的条目必须用分号分隔, 后跟空格。</span><span class="sxs-lookup"><span data-stu-id="68bf9-118">Separate entries must be delimited by a semicolon followed by a space.</span></span> <span data-ttu-id="68bf9-119">此属性不是必需的。</span><span class="sxs-lookup"><span data-stu-id="68bf9-119">This property is not required.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="68bf9-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="68bf9-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="68bf9-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="68bf9-121">Protocol specifications</span></span>

<span data-ttu-id="68bf9-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68bf9-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68bf9-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="68bf9-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="68bf9-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="68bf9-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="68bf9-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="68bf9-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="68bf9-126">头文件</span><span class="sxs-lookup"><span data-stu-id="68bf9-126">Header files</span></span>

<span data-ttu-id="68bf9-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="68bf9-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="68bf9-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="68bf9-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="68bf9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68bf9-129">See also</span></span>



[<span data-ttu-id="68bf9-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="68bf9-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="68bf9-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="68bf9-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="68bf9-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="68bf9-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="68bf9-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="68bf9-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

