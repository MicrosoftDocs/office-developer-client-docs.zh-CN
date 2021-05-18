---
title: PidTagScheduleInfoDelegateEntryIds 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDelegateEntryIds
api_type:
- COM
ms.assetid: c178a4e4-6f4c-409c-9db3-f6338bd4f40f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b2adde7c5ecc75fda25b94d005fabfcd705d5d07
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321292"
---
# <a name="pidtagscheduleinfodelegateentryids-canonical-property"></a><span data-ttu-id="74de5-103">PidTagScheduleInfoDelegateEntryIds 规范属性</span><span class="sxs-lookup"><span data-stu-id="74de5-103">PidTagScheduleInfoDelegateEntryIds Canonical Property</span></span>

  
  
<span data-ttu-id="74de5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74de5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74de5-105">包含 **委托的 EntryID。**</span><span class="sxs-lookup"><span data-stu-id="74de5-105">Contains the **EntryIDs** of the delegates.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="74de5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="74de5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="74de5-107">PR_SCHDINFO_DELEGATE_ENTRYIDS</span><span class="sxs-lookup"><span data-stu-id="74de5-107">PR_SCHDINFO_DELEGATE_ENTRYIDS</span></span>  <br/> |
|<span data-ttu-id="74de5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="74de5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="74de5-109">0x6845</span><span class="sxs-lookup"><span data-stu-id="74de5-109">0x6845</span></span>  <br/> |
|<span data-ttu-id="74de5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="74de5-110">Data type:</span></span>  <br/> |<span data-ttu-id="74de5-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="74de5-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="74de5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="74de5-112">Area:</span></span>  <br/> |<span data-ttu-id="74de5-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="74de5-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="74de5-114">备注</span><span class="sxs-lookup"><span data-stu-id="74de5-114">Remarks</span></span>

<span data-ttu-id="74de5-115">每个条目必须包含每个代理通讯簿PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性的值。 </span><span class="sxs-lookup"><span data-stu-id="74de5-115">Each entry must contain the value of the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property of each delegate's address book entry.</span></span> <span data-ttu-id="74de5-116">此属性必须在委托信息对象中设置。</span><span class="sxs-lookup"><span data-stu-id="74de5-116">This property must be set in the delegate information object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="74de5-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="74de5-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="74de5-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="74de5-118">Protocol specifications</span></span>

<span data-ttu-id="74de5-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="74de5-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="74de5-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="74de5-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="74de5-121">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="74de5-121">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="74de5-122">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="74de5-122">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="74de5-123">头文件</span><span class="sxs-lookup"><span data-stu-id="74de5-123">Header files</span></span>

<span data-ttu-id="74de5-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="74de5-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="74de5-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="74de5-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="74de5-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="74de5-126">Mapitags.h</span></span>
  
> <span data-ttu-id="74de5-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="74de5-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="74de5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74de5-128">See also</span></span>



[<span data-ttu-id="74de5-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="74de5-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="74de5-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="74de5-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="74de5-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="74de5-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="74de5-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="74de5-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

