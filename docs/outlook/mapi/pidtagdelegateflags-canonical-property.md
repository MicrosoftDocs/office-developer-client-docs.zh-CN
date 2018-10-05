---
title: PidTagDelegateFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDelegateFlags
api_type:
- HeaderDef
ms.assetid: 3a504594-204c-472c-8be7-dca154c94ea2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 20ffc6f7f4d21f980e5f0f387464430ba187192a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392275"
---
# <a name="pidtagdelegateflags-canonical-property"></a><span data-ttu-id="3a1ba-103">PidTagDelegateFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a1ba-103">PidTagDelegateFlags Canonical Property</span></span>

  
  
<span data-ttu-id="3a1ba-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a1ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a1ba-105">指定代理人是否可查看 delegator 私有消息对象。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-105">Specifies whether a delegate can view the delegator's private message objects.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3a1ba-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a1ba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a1ba-107">PR_DELEGATE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="3a1ba-107">PR_DELEGATE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="3a1ba-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3a1ba-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3a1ba-109">0x686B</span><span class="sxs-lookup"><span data-stu-id="3a1ba-109">0x686B</span></span>  <br/> |
|<span data-ttu-id="3a1ba-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a1ba-110">Data type:</span></span>  <br/> |<span data-ttu-id="3a1ba-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="3a1ba-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="3a1ba-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3a1ba-112">Area:</span></span>  <br/> |<span data-ttu-id="3a1ba-113">类定义消息可传送</span><span class="sxs-lookup"><span data-stu-id="3a1ba-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a1ba-114">说明</span><span class="sxs-lookup"><span data-stu-id="3a1ba-114">Remarks</span></span>

<span data-ttu-id="3a1ba-115">每个条目的此属性必须设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-115">Each entry of this property must be set to one of the following values.</span></span>
  
|<span data-ttu-id="3a1ba-116">**Flag**</span><span class="sxs-lookup"><span data-stu-id="3a1ba-116">**Flag**</span></span>|<span data-ttu-id="3a1ba-117">**值**</span><span class="sxs-lookup"><span data-stu-id="3a1ba-117">**Value**</span></span>|<span data-ttu-id="3a1ba-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="3a1ba-118">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a1ba-119">HidePrivate</span><span class="sxs-lookup"><span data-stu-id="3a1ba-119">HidePrivate</span></span>  <br/> |<span data-ttu-id="3a1ba-120">0</span><span class="sxs-lookup"><span data-stu-id="3a1ba-120">0</span></span>  <br/> |<span data-ttu-id="3a1ba-121">该委托不应允许查看私有消息对象。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-121">The delegate should not be allowed to view private message objects.</span></span>  <br/> |
|<span data-ttu-id="3a1ba-122">ShowPrivate</span><span class="sxs-lookup"><span data-stu-id="3a1ba-122">ShowPrivate</span></span>  <br/> |<span data-ttu-id="3a1ba-123">1</span><span class="sxs-lookup"><span data-stu-id="3a1ba-123">1</span></span>  <br/> |<span data-ttu-id="3a1ba-124">应允许委托查看私有消息对象。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-124">The delegate should be allowed to view private message objects.</span></span>  <br/> |
   
<span data-ttu-id="3a1ba-125">此属性必须设置委托信息对象中。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-125">This property must be set in the delegate information object.</span></span> <span data-ttu-id="3a1ba-126">"ShowPrivate"的值指示代理者希望公开私有消息对象。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-126">The value of "ShowPrivate" indicates that the delegator wants to make private message objects visible.</span></span> <span data-ttu-id="3a1ba-127">适用于所有文件夹委托有审阅者、 作者或编辑器角色此首选项。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-127">This preference is applicable to all folders for which the delegate has a role of reviewer, author, or editor.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3a1ba-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="3a1ba-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3a1ba-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="3a1ba-129">Protocol specifications</span></span>

<span data-ttu-id="3a1ba-130">[[MS OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3a1ba-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3a1ba-131">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-131">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3a1ba-132">头文件</span><span class="sxs-lookup"><span data-stu-id="3a1ba-132">Header files</span></span>

<span data-ttu-id="3a1ba-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3a1ba-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="3a1ba-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="3a1ba-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3a1ba-135">Mapitags.h</span></span>
  
> <span data-ttu-id="3a1ba-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3a1ba-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3a1ba-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a1ba-137">See also</span></span>



[<span data-ttu-id="3a1ba-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3a1ba-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3a1ba-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a1ba-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3a1ba-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3a1ba-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3a1ba-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3a1ba-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

