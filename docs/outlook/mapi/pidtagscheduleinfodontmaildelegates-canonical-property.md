---
title: PidTagScheduleInfoDontMailDelegates 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDontMailDelegates
api_type:
- COM
ms.assetid: e932966e-cb7a-4d8b-8f06-6406fce1b3e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f5965d75e72cecf11216ae785632f7e830a98178
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330105"
---
# <a name="pidtagscheduleinfodontmaildelegates-canonical-property"></a><span data-ttu-id="c9039-103">PidTagScheduleInfoDontMailDelegates 规范属性</span><span class="sxs-lookup"><span data-stu-id="c9039-103">PidTagScheduleInfoDontMailDelegates Canonical Property</span></span>

  
  
<span data-ttu-id="c9039-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c9039-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c9039-105">如果代理不想接收更新, 则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c9039-105">Contains TRUE if the delegate does not want to receive updates.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c9039-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c9039-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c9039-107">PR_SCHDINFO_DONT_MAIL_DELEGATES</span><span class="sxs-lookup"><span data-stu-id="c9039-107">PR_SCHDINFO_DONT_MAIL_DELEGATES</span></span>  <br/> |
|<span data-ttu-id="c9039-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c9039-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c9039-109">0x6843</span><span class="sxs-lookup"><span data-stu-id="c9039-109">0x6843</span></span>  <br/> |
|<span data-ttu-id="c9039-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c9039-110">Data type:</span></span>  <br/> |<span data-ttu-id="c9039-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c9039-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c9039-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c9039-112">Area:</span></span>  <br/> |<span data-ttu-id="c9039-113">闲/忙</span><span class="sxs-lookup"><span data-stu-id="c9039-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c9039-114">注解</span><span class="sxs-lookup"><span data-stu-id="c9039-114">Remarks</span></span>

<span data-ttu-id="c9039-115">此属性必须在 "代理信息" 对象中设置。</span><span class="sxs-lookup"><span data-stu-id="c9039-115">This property must be set in the delegate information object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c9039-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="c9039-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c9039-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="c9039-117">Protocol specifications</span></span>

<span data-ttu-id="c9039-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c9039-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c9039-119">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c9039-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c9039-120">[[毫秒-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c9039-120">[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c9039-121">发布用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="c9039-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c9039-122">头文件</span><span class="sxs-lookup"><span data-stu-id="c9039-122">Header files</span></span>

<span data-ttu-id="c9039-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c9039-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="c9039-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c9039-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="c9039-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c9039-125">Mapitags.h</span></span>
  
> <span data-ttu-id="c9039-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c9039-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c9039-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9039-127">See also</span></span>



[<span data-ttu-id="c9039-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c9039-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c9039-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c9039-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c9039-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c9039-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c9039-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c9039-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

