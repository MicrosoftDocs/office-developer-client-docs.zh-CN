---
title: PidTagScheduleInfoDelegatorWantsCopy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDelegatorWantsCopy
api_type:
- COM
ms.assetid: 48e48e3a-1186-46c4-8ff9-34e03905fb93
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5910fd60b7837c2f170358dd5cd4e3306e4c1770
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778352"
---
# <a name="pidtagscheduleinfodelegatorwantscopy-canonical-property"></a><span data-ttu-id="e92e1-103">PidTagScheduleInfoDelegatorWantsCopy 规范属性</span><span class="sxs-lookup"><span data-stu-id="e92e1-103">PidTagScheduleInfoDelegatorWantsCopy Canonical Property</span></span>

  
  
<span data-ttu-id="e92e1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e92e1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e92e1-105">包含 TRUE，如果代理者希望接收副本发送给代理的会议相关对象。</span><span class="sxs-lookup"><span data-stu-id="e92e1-105">Contains TRUE if the delegator wants to receive copies of the meeting-related objects that are sent to the delegate.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e92e1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e92e1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e92e1-107">PR_SCHDINFO_BOSS_WANTS_COPY</span><span class="sxs-lookup"><span data-stu-id="e92e1-107">PR_SCHDINFO_BOSS_WANTS_COPY</span></span>  <br/> |
|<span data-ttu-id="e92e1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="e92e1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e92e1-109">0x6842</span><span class="sxs-lookup"><span data-stu-id="e92e1-109">0x6842</span></span>  <br/> |
|<span data-ttu-id="e92e1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e92e1-110">Data type:</span></span>  <br/> |<span data-ttu-id="e92e1-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="e92e1-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="e92e1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e92e1-112">Area:</span></span>  <br/> |<span data-ttu-id="e92e1-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="e92e1-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e92e1-114">说明</span><span class="sxs-lookup"><span data-stu-id="e92e1-114">Remarks</span></span>

<span data-ttu-id="e92e1-115">此属性必须设置委托信息对象中。</span><span class="sxs-lookup"><span data-stu-id="e92e1-115">This property must be set in the delegate information object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e92e1-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="e92e1-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e92e1-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="e92e1-117">Protocol specifications</span></span>

<span data-ttu-id="e92e1-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e92e1-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e92e1-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="e92e1-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e92e1-120">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e92e1-120">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e92e1-121">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="e92e1-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="e92e1-122">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e92e1-122">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e92e1-123">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="e92e1-123">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e92e1-124">头文件</span><span class="sxs-lookup"><span data-stu-id="e92e1-124">Header files</span></span>

<span data-ttu-id="e92e1-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e92e1-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="e92e1-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e92e1-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="e92e1-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e92e1-127">Mapitags.h</span></span>
  
> <span data-ttu-id="e92e1-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e92e1-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e92e1-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e92e1-129">See also</span></span>



[<span data-ttu-id="e92e1-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e92e1-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e92e1-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e92e1-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e92e1-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e92e1-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e92e1-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e92e1-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

