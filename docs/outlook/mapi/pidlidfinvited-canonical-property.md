---
title: PidLidFInvited 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFInvited
api_type:
- COM
ms.assetid: ca1ea5ec-20d5-4b70-95de-c2246a10beae
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3c2ddb5da9202e9cf0d1c78da1c1ad085ef9687c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357797"
---
# <a name="pidlidfinvited-canonical-property"></a><span data-ttu-id="52232-103">PidLidFInvited 规范属性</span><span class="sxs-lookup"><span data-stu-id="52232-103">PidLidFInvited Canonical Property</span></span>

  
  
<span data-ttu-id="52232-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52232-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52232-105">指示是否已为此会议代表的会议发送了邀请。</span><span class="sxs-lookup"><span data-stu-id="52232-105">Indicates whether or not invitations have been sent for the meeting that this meeting represents.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52232-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="52232-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="52232-107">dispidFInvited</span><span class="sxs-lookup"><span data-stu-id="52232-107">dispidFInvited</span></span>  <br/> |
|<span data-ttu-id="52232-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="52232-108">Property set:</span></span>  <br/> |<span data-ttu-id="52232-109">PSETID_Appointment</span><span class="sxs-lookup"><span data-stu-id="52232-109">PSETID_Appointment</span></span>  <br/> |
|<span data-ttu-id="52232-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="52232-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="52232-111">0x00008229</span><span class="sxs-lookup"><span data-stu-id="52232-111">0x00008229</span></span>  <br/> |
|<span data-ttu-id="52232-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="52232-112">Data type:</span></span>  <br/> |<span data-ttu-id="52232-113">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="52232-113">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="52232-114">区域：</span><span class="sxs-lookup"><span data-stu-id="52232-114">Area:</span></span>  <br/> |<span data-ttu-id="52232-115">会议</span><span class="sxs-lookup"><span data-stu-id="52232-115">Meetings</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52232-116">注解</span><span class="sxs-lookup"><span data-stu-id="52232-116">Remarks</span></span>

<span data-ttu-id="52232-117">值为 FALSE, 或缺少此属性时, 表示会议请求从未发送过。</span><span class="sxs-lookup"><span data-stu-id="52232-117">A value of FALSE, or the absence of this property, indicates that a meeting request has never been sent.</span></span> <span data-ttu-id="52232-118">如果值为 TRUE, 则表示已发送会议请求。</span><span class="sxs-lookup"><span data-stu-id="52232-118">A value of TRUE indicates that a meeting request has been sent.</span></span> <span data-ttu-id="52232-119">一旦会议上将此值设置为 TRUE, 则不得更改它。</span><span class="sxs-lookup"><span data-stu-id="52232-119">Once this value is set to TRUE on a meeting, it must not be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="52232-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="52232-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="52232-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="52232-121">Protocol specifications</span></span>

<span data-ttu-id="52232-122">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="52232-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="52232-123">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="52232-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="52232-124">[[毫秒-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="52232-124">[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="52232-125">指定约会、会议请求和响应邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="52232-125">Specifies the properties and operations for appointment, meeting request, and response messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="52232-126">头文件</span><span class="sxs-lookup"><span data-stu-id="52232-126">Header files</span></span>

<span data-ttu-id="52232-127">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="52232-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="52232-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="52232-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="52232-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52232-129">See also</span></span>



[<span data-ttu-id="52232-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="52232-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="52232-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="52232-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="52232-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="52232-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="52232-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="52232-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

