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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6bcda9c6281e25f3bae2f9c1dda2f8defb024b57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778339"
---
# <a name="pidtagscheduleinfodontmaildelegates-canonical-property"></a><span data-ttu-id="6db3e-103">PidTagScheduleInfoDontMailDelegates 规范属性</span><span class="sxs-lookup"><span data-stu-id="6db3e-103">PidTagScheduleInfoDontMailDelegates Canonical Property</span></span>

  
  
<span data-ttu-id="6db3e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6db3e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6db3e-105">如果该委托不希望接收更新，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6db3e-105">Contains TRUE if the delegate does not want to receive updates.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6db3e-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6db3e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6db3e-107">PR_SCHDINFO_DONT_MAIL_DELEGATES</span><span class="sxs-lookup"><span data-stu-id="6db3e-107">PR_SCHDINFO_DONT_MAIL_DELEGATES</span></span>  <br/> |
|<span data-ttu-id="6db3e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="6db3e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6db3e-109">0x6843</span><span class="sxs-lookup"><span data-stu-id="6db3e-109">0x6843</span></span>  <br/> |
|<span data-ttu-id="6db3e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6db3e-110">Data type:</span></span>  <br/> |<span data-ttu-id="6db3e-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6db3e-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6db3e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6db3e-112">Area:</span></span>  <br/> |<span data-ttu-id="6db3e-113">忙/闲</span><span class="sxs-lookup"><span data-stu-id="6db3e-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6db3e-114">备注</span><span class="sxs-lookup"><span data-stu-id="6db3e-114">Remarks</span></span>

<span data-ttu-id="6db3e-115">此属性必须设置委托信息对象中。</span><span class="sxs-lookup"><span data-stu-id="6db3e-115">This property must be set in the delegate information object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6db3e-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="6db3e-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6db3e-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="6db3e-117">Protocol specifications</span></span>

<span data-ttu-id="6db3e-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6db3e-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6db3e-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6db3e-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6db3e-120">[[MS OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6db3e-120">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6db3e-121">发布的用户或资源的可用性。</span><span class="sxs-lookup"><span data-stu-id="6db3e-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6db3e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="6db3e-122">Header files</span></span>

<span data-ttu-id="6db3e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6db3e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="6db3e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6db3e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="6db3e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6db3e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="6db3e-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6db3e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6db3e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6db3e-127">See also</span></span>



[<span data-ttu-id="6db3e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6db3e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6db3e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6db3e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6db3e-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6db3e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6db3e-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6db3e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

