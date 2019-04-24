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
ms.openlocfilehash: c52a1c055792f17477ff5540c4138160544e3b18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321306"
---
# <a name="pidtagscheduleinfodelegatorwantscopy-canonical-property"></a><span data-ttu-id="34418-103">PidTagScheduleInfoDelegatorWantsCopy 规范属性</span><span class="sxs-lookup"><span data-stu-id="34418-103">PidTagScheduleInfoDelegatorWantsCopy Canonical Property</span></span>

  
  
<span data-ttu-id="34418-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34418-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34418-105">如果代理者想要接收发送给代理的与会议相关的对象的副本, 则该参数为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="34418-105">Contains TRUE if the delegator wants to receive copies of the meeting-related objects that are sent to the delegate.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="34418-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="34418-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="34418-107">PR_SCHDINFO_BOSS_WANTS_COPY</span><span class="sxs-lookup"><span data-stu-id="34418-107">PR_SCHDINFO_BOSS_WANTS_COPY</span></span>  <br/> |
|<span data-ttu-id="34418-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="34418-108">Identifier:</span></span>  <br/> |<span data-ttu-id="34418-109">0x6842</span><span class="sxs-lookup"><span data-stu-id="34418-109">0x6842</span></span>  <br/> |
|<span data-ttu-id="34418-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="34418-110">Data type:</span></span>  <br/> |<span data-ttu-id="34418-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="34418-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="34418-112">区域：</span><span class="sxs-lookup"><span data-stu-id="34418-112">Area:</span></span>  <br/> |<span data-ttu-id="34418-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="34418-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="34418-114">注解</span><span class="sxs-lookup"><span data-stu-id="34418-114">Remarks</span></span>

<span data-ttu-id="34418-115">此属性必须在 "代理信息" 对象中设置。</span><span class="sxs-lookup"><span data-stu-id="34418-115">This property must be set in the delegate information object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="34418-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="34418-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="34418-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="34418-117">Protocol specifications</span></span>

<span data-ttu-id="34418-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34418-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34418-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="34418-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="34418-120">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34418-120">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34418-121">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="34418-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="34418-122">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="34418-122">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="34418-123">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="34418-123">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="34418-124">头文件</span><span class="sxs-lookup"><span data-stu-id="34418-124">Header files</span></span>

<span data-ttu-id="34418-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="34418-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="34418-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="34418-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="34418-127">Mapitags</span><span class="sxs-lookup"><span data-stu-id="34418-127">Mapitags.h</span></span>
  
> <span data-ttu-id="34418-128">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="34418-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34418-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34418-129">See also</span></span>



[<span data-ttu-id="34418-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="34418-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="34418-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="34418-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="34418-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="34418-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="34418-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="34418-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

