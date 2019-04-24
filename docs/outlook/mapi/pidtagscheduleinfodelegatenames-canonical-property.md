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
ms.openlocfilehash: a257934411bb11a30378ee46317d323156f53e31
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314936"
---
# <a name="pidtagscheduleinfodelegatenames-canonical-property"></a><span data-ttu-id="b83b3-103">PidTagScheduleInfoDelegateNames 规范属性</span><span class="sxs-lookup"><span data-stu-id="b83b3-103">PidTagScheduleInfoDelegateNames Canonical Property</span></span>

  
  
<span data-ttu-id="b83b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b83b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b83b3-105">包含代理的名称。</span><span class="sxs-lookup"><span data-stu-id="b83b3-105">Contains the names of the delegates.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b83b3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b83b3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b83b3-107">PR_SCHDINFO_DELEGATE_NAMES、PR_SCHDINFO_DELEGATE_NAMES_A、PR_SCHDINFO_DELEGATE_NAMES_W</span><span class="sxs-lookup"><span data-stu-id="b83b3-107">PR_SCHDINFO_DELEGATE_NAMES, PR_SCHDINFO_DELEGATE_NAMES_A, PR_SCHDINFO_DELEGATE_NAMES_W</span></span>  <br/> |
|<span data-ttu-id="b83b3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b83b3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b83b3-109">0x6844</span><span class="sxs-lookup"><span data-stu-id="b83b3-109">0x6844</span></span>  <br/> |
|<span data-ttu-id="b83b3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b83b3-110">Data type:</span></span>  <br/> |<span data-ttu-id="b83b3-111">PT_MV_STRING8、PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b83b3-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b83b3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b83b3-112">Area:</span></span>  <br/> |<span data-ttu-id="b83b3-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="b83b3-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b83b3-114">注解</span><span class="sxs-lookup"><span data-stu-id="b83b3-114">Remarks</span></span>

<span data-ttu-id="b83b3-115">这些属性中的每个条目都必须包含每个代理的通讯簿的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b83b3-115">Each entry in these properties must contain the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property of each delegate's address book.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b83b3-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="b83b3-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b83b3-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="b83b3-117">Protocol specifications</span></span>

<span data-ttu-id="b83b3-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b83b3-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b83b3-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b83b3-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b83b3-120">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b83b3-120">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b83b3-121">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="b83b3-121">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b83b3-122">头文件</span><span class="sxs-lookup"><span data-stu-id="b83b3-122">Header files</span></span>

<span data-ttu-id="b83b3-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b83b3-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="b83b3-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b83b3-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="b83b3-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b83b3-125">Mapitags.h</span></span>
  
> <span data-ttu-id="b83b3-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b83b3-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b83b3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b83b3-127">See also</span></span>



[<span data-ttu-id="b83b3-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b83b3-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b83b3-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b83b3-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b83b3-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b83b3-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b83b3-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b83b3-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

