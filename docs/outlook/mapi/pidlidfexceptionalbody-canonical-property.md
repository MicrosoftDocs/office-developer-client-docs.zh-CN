---
title: PidLidFExceptionalBody 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFExceptionalBody
api_type:
- COM
ms.assetid: 327516e8-ed3f-40fc-9604-03a70aecef5a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 93eb98aee19ea3f46a4e01e2c80150c3efe893a5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393899"
---
# <a name="pidlidfexceptionalbody-canonical-property"></a><span data-ttu-id="dc1ad-103">PidLidFExceptionalBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc1ad-103">PidLidFExceptionalBody Canonical Property</span></span>

  
  
<span data-ttu-id="dc1ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc1ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc1ad-105">指示例外嵌入对象具有一个不同的定期 calendar 对象的主体的消息。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-105">Indicates that the exception embedded message object has a body that differs from the recurring calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dc1ad-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="dc1ad-107">dispidFExceptionalBody</span><span class="sxs-lookup"><span data-stu-id="dc1ad-107">dispidFExceptionalBody</span></span>  <br/> |
|<span data-ttu-id="dc1ad-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-108">Property set:</span></span>  <br/> |<span data-ttu-id="dc1ad-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="dc1ad-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="dc1ad-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="dc1ad-111">0x00008206</span><span class="sxs-lookup"><span data-stu-id="dc1ad-111">0x00008206</span></span>  <br/> |
|<span data-ttu-id="dc1ad-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-112">Data type:</span></span>  <br/> |<span data-ttu-id="dc1ad-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="dc1ad-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="dc1ad-114">区域：</span><span class="sxs-lookup"><span data-stu-id="dc1ad-114">Area:</span></span>  <br/> |<span data-ttu-id="dc1ad-115">会议</span><span class="sxs-lookup"><span data-stu-id="dc1ad-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dc1ad-116">说明</span><span class="sxs-lookup"><span data-stu-id="dc1ad-116">Remarks</span></span>

<span data-ttu-id="dc1ad-117">如果此属性的值为 TRUE，然后例外嵌入的对象必须具有正文的邮件。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-117">If the value of this property is TRUE, then the exception embedded message object must have a body.</span></span> <span data-ttu-id="dc1ad-118">如果此属性的值为 FALSE，或者如果属性不存在，客户端或服务器必须获得定期 calendar 对象的正文。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-118">If the value of this property is FALSE, or if the property does not exist, then a client or server must obtain the body from the recurring calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="dc1ad-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="dc1ad-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="dc1ad-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="dc1ad-120">Protocol specifications</span></span>

<span data-ttu-id="dc1ad-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc1ad-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc1ad-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="dc1ad-123">[[MS OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="dc1ad-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="dc1ad-124">指定的属性和约会、 会议请求和响应消息的操作。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="dc1ad-125">头文件</span><span class="sxs-lookup"><span data-stu-id="dc1ad-125">Header files</span></span>

<span data-ttu-id="dc1ad-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc1ad-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="dc1ad-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="dc1ad-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dc1ad-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc1ad-128">See also</span></span>



[<span data-ttu-id="dc1ad-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="dc1ad-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="dc1ad-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="dc1ad-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="dc1ad-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="dc1ad-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="dc1ad-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="dc1ad-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

