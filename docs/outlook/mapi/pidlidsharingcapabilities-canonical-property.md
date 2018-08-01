---
title: PidLidSharingCapabilities 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingCapabilities
api_type:
- COM
ms.assetid: 86b3eab2-2594-4204-aedf-8ce2ee3b81ce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 73f39c0b97ebcd5c84bb908b62f758eaacd4eabf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777019"
---
# <a name="pidlidsharingcapabilities-canonical-property"></a><span data-ttu-id="6786d-103">PidLidSharingCapabilities 规范属性</span><span class="sxs-lookup"><span data-stu-id="6786d-103">PidLidSharingCapabilities Canonical Property</span></span>

  
  
<span data-ttu-id="6786d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6786d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6786d-105">将指定的共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="6786d-105">Designates as a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6786d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6786d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6786d-107">dispidSharingCaps</span><span class="sxs-lookup"><span data-stu-id="6786d-107">dispidSharingCaps</span></span>  <br/> |
|<span data-ttu-id="6786d-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6786d-108">Property set:</span></span>  <br/> |<span data-ttu-id="6786d-109">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="6786d-109">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="6786d-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6786d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6786d-111">0x00008A17</span><span class="sxs-lookup"><span data-stu-id="6786d-111">0x00008A17</span></span>  <br/> |
|<span data-ttu-id="6786d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6786d-112">Data type:</span></span>  <br/> |<span data-ttu-id="6786d-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6786d-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6786d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6786d-114">Area:</span></span>  <br/> |<span data-ttu-id="6786d-115">共享</span><span class="sxs-lookup"><span data-stu-id="6786d-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6786d-116">说明</span><span class="sxs-lookup"><span data-stu-id="6786d-116">Remarks</span></span>

<span data-ttu-id="6786d-117">此属性必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="6786d-117">This property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="6786d-118">**值**</span><span class="sxs-lookup"><span data-stu-id="6786d-118">**Value**</span></span>|<span data-ttu-id="6786d-119">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="6786d-119">**Scenario**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6786d-120">0x00040290</span><span class="sxs-lookup"><span data-stu-id="6786d-120">0x00040290</span></span>  <br/> |<span data-ttu-id="6786d-121">此共享邮件对象关联到的特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="6786d-121">This Sharing Message object relates to a special folder.</span></span>  <br/> |
|<span data-ttu-id="6786d-122">0x000402B0</span><span class="sxs-lookup"><span data-stu-id="6786d-122">0x000402B0</span></span>  <br/> |<span data-ttu-id="6786d-123">此共享邮件对象不与相关的特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="6786d-123">This Sharing Message object does not relate to a special folder.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="6786d-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="6786d-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6786d-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="6786d-125">Protocol specifications</span></span>

<span data-ttu-id="6786d-126">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6786d-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6786d-127">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6786d-127">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6786d-128">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6786d-128">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6786d-129">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="6786d-129">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6786d-130">头文件</span><span class="sxs-lookup"><span data-stu-id="6786d-130">Header files</span></span>

<span data-ttu-id="6786d-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6786d-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="6786d-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6786d-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6786d-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6786d-133">See also</span></span>



[<span data-ttu-id="6786d-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6786d-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6786d-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6786d-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6786d-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6786d-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6786d-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6786d-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

