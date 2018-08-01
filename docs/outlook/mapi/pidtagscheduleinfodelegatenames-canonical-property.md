---
title: PidTagScheduleInfoDelegateNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDelegateNames
api_type:
- COM
ms.assetid: 592d9c78-4487-4c68-8ae7-4cd3d6265685
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fed2b23680cd2654bbb6960e3c6be07074307a98
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778315"
---
# <a name="pidtagscheduleinfodelegatenames-canonical-property"></a><span data-ttu-id="1f92e-103">PidTagScheduleInfoDelegateNames 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f92e-103">PidTagScheduleInfoDelegateNames Canonical Property</span></span>

  
  
<span data-ttu-id="1f92e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1f92e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1f92e-105">包含的代理人的名称。</span><span class="sxs-lookup"><span data-stu-id="1f92e-105">Contains the names of the delegates.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1f92e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1f92e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1f92e-107">PR_SCHDINFO_DELEGATE_NAMES，PR_SCHDINFO_DELEGATE_NAMES_A，PR_SCHDINFO_DELEGATE_NAMES_W</span><span class="sxs-lookup"><span data-stu-id="1f92e-107">PR_SCHDINFO_DELEGATE_NAMES, PR_SCHDINFO_DELEGATE_NAMES_A, PR_SCHDINFO_DELEGATE_NAMES_W</span></span>  <br/> |
|<span data-ttu-id="1f92e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1f92e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1f92e-109">0x6844</span><span class="sxs-lookup"><span data-stu-id="1f92e-109">0x6844</span></span>  <br/> |
|<span data-ttu-id="1f92e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1f92e-110">Data type:</span></span>  <br/> |<span data-ttu-id="1f92e-111">PT_MV_STRING8 PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1f92e-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1f92e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1f92e-112">Area:</span></span>  <br/> |<span data-ttu-id="1f92e-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="1f92e-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1f92e-114">说明</span><span class="sxs-lookup"><span data-stu-id="1f92e-114">Remarks</span></span>

<span data-ttu-id="1f92e-115">这些属性中的每个条目都必须包含的每个代理人的通讯簿**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1f92e-115">Each entry in these properties must contain the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of each delegate's address book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1f92e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="1f92e-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1f92e-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="1f92e-117">Protocol specifications</span></span>

<span data-ttu-id="1f92e-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f92e-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f92e-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1f92e-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1f92e-120">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1f92e-120">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1f92e-121">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="1f92e-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1f92e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="1f92e-122">Header files</span></span>

<span data-ttu-id="1f92e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1f92e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="1f92e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1f92e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="1f92e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1f92e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="1f92e-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1f92e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1f92e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f92e-127">See also</span></span>



[<span data-ttu-id="1f92e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1f92e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1f92e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1f92e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1f92e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1f92e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1f92e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1f92e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

