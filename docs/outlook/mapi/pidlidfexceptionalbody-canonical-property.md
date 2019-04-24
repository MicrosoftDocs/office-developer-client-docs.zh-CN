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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327459"
---
# <a name="pidlidfexceptionalbody-canonical-property"></a><span data-ttu-id="2cf95-103">PidLidFExceptionalBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="2cf95-103">PidLidFExceptionalBody Canonical Property</span></span>

  
  
<span data-ttu-id="2cf95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2cf95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2cf95-105">指示异常嵌入邮件对象具有与定期日历对象不同的正文。</span><span class="sxs-lookup"><span data-stu-id="2cf95-105">Indicates that the exception embedded message object has a body that differs from the recurring calendar object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2cf95-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2cf95-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2cf95-107">dispidFExceptionalBody</span><span class="sxs-lookup"><span data-stu-id="2cf95-107">dispidFExceptionalBody</span></span>  <br/> |
|<span data-ttu-id="2cf95-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="2cf95-108">Property set:</span></span>  <br/> |<span data-ttu-id="2cf95-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="2cf95-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="2cf95-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="2cf95-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2cf95-111">0x00008206</span><span class="sxs-lookup"><span data-stu-id="2cf95-111">0x00008206</span></span>  <br/> |
|<span data-ttu-id="2cf95-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2cf95-112">Data type:</span></span>  <br/> |<span data-ttu-id="2cf95-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="2cf95-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="2cf95-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2cf95-114">Area:</span></span>  <br/> |<span data-ttu-id="2cf95-115">会议</span><span class="sxs-lookup"><span data-stu-id="2cf95-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2cf95-116">注解</span><span class="sxs-lookup"><span data-stu-id="2cf95-116">Remarks</span></span>

<span data-ttu-id="2cf95-117">如果此属性的值为 TRUE, 则异常嵌入邮件对象必须具有正文。</span><span class="sxs-lookup"><span data-stu-id="2cf95-117">If the value of this property is TRUE, then the exception embedded message object must have a body.</span></span> <span data-ttu-id="2cf95-118">如果此属性的值为 FALSE, 或者属性不存在, 则客户端或服务器必须从定期日历对象中获取正文。</span><span class="sxs-lookup"><span data-stu-id="2cf95-118">If the value of this property is FALSE, or if the property does not exist, then a client or server must obtain the body from the recurring calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2cf95-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2cf95-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2cf95-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2cf95-120">Protocol specifications</span></span>

<span data-ttu-id="2cf95-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2cf95-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2cf95-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2cf95-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2cf95-123">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2cf95-123">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2cf95-124">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="2cf95-124">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2cf95-125">头文件</span><span class="sxs-lookup"><span data-stu-id="2cf95-125">Header files</span></span>

<span data-ttu-id="2cf95-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2cf95-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="2cf95-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2cf95-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2cf95-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf95-128">See also</span></span>



[<span data-ttu-id="2cf95-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2cf95-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2cf95-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2cf95-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2cf95-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2cf95-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2cf95-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2cf95-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

