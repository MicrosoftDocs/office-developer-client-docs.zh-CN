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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359897"
---
# <a name="pidtagdelegateflags-canonical-property"></a><span data-ttu-id="e9944-103">PidTagDelegateFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9944-103">PidTagDelegateFlags Canonical Property</span></span>

  
  
<span data-ttu-id="e9944-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e9944-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e9944-105">指定代理是否可以查看代理者的私人邮件对象。</span><span class="sxs-lookup"><span data-stu-id="e9944-105">Specifies whether a delegate can view the delegator's private message objects.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e9944-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e9944-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e9944-107">PR_DELEGATE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="e9944-107">PR_DELEGATE_FLAGS</span></span>  <br/> |
|<span data-ttu-id="e9944-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e9944-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e9944-109">0x686B</span><span class="sxs-lookup"><span data-stu-id="e9944-109">0x686B</span></span>  <br/> |
|<span data-ttu-id="e9944-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e9944-110">Data type:</span></span>  <br/> |<span data-ttu-id="e9944-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="e9944-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="e9944-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e9944-112">Area:</span></span>  <br/> |<span data-ttu-id="e9944-113">邮件类定义的可传输</span><span class="sxs-lookup"><span data-stu-id="e9944-113">Message class-defined transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e9944-114">备注</span><span class="sxs-lookup"><span data-stu-id="e9944-114">Remarks</span></span>

<span data-ttu-id="e9944-115">此属性的每个条目必须设置为下列值之一。</span><span class="sxs-lookup"><span data-stu-id="e9944-115">Each entry of this property must be set to one of the following values.</span></span>
  
|<span data-ttu-id="e9944-116">**Flag**</span><span class="sxs-lookup"><span data-stu-id="e9944-116">**Flag**</span></span>|<span data-ttu-id="e9944-117">**值**</span><span class="sxs-lookup"><span data-stu-id="e9944-117">**Value**</span></span>|<span data-ttu-id="e9944-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="e9944-118">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9944-119">HidePrivate</span><span class="sxs-lookup"><span data-stu-id="e9944-119">HidePrivate</span></span>  <br/> |<span data-ttu-id="e9944-120">0</span><span class="sxs-lookup"><span data-stu-id="e9944-120">0</span></span>  <br/> |<span data-ttu-id="e9944-121">不应允许代理查看私人邮件对象。</span><span class="sxs-lookup"><span data-stu-id="e9944-121">The delegate should not be allowed to view private message objects.</span></span>  <br/> |
|<span data-ttu-id="e9944-122">ShowPrivate</span><span class="sxs-lookup"><span data-stu-id="e9944-122">ShowPrivate</span></span>  <br/> |<span data-ttu-id="e9944-123">1</span><span class="sxs-lookup"><span data-stu-id="e9944-123">1</span></span>  <br/> |<span data-ttu-id="e9944-124">应允许代理查看私人邮件对象。</span><span class="sxs-lookup"><span data-stu-id="e9944-124">The delegate should be allowed to view private message objects.</span></span>  <br/> |
   
<span data-ttu-id="e9944-125">此属性必须在委托信息对象中设置。</span><span class="sxs-lookup"><span data-stu-id="e9944-125">This property must be set in the delegate information object.</span></span> <span data-ttu-id="e9944-126">"ShowPrivate"的值指示委派者希望使私人邮件对象可见。</span><span class="sxs-lookup"><span data-stu-id="e9944-126">The value of "ShowPrivate" indicates that the delegator wants to make private message objects visible.</span></span> <span data-ttu-id="e9944-127">此首选项适用于代理具有审阅者、作者或编辑者角色的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="e9944-127">This preference is applicable to all folders for which the delegate has a role of reviewer, author, or editor.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e9944-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="e9944-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e9944-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="e9944-129">Protocol specifications</span></span>

<span data-ttu-id="e9944-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e9944-130">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e9944-131">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="e9944-131">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e9944-132">头文件</span><span class="sxs-lookup"><span data-stu-id="e9944-132">Header files</span></span>

<span data-ttu-id="e9944-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e9944-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="e9944-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e9944-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="e9944-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e9944-135">Mapitags.h</span></span>
  
> <span data-ttu-id="e9944-136">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e9944-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e9944-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9944-137">See also</span></span>



[<span data-ttu-id="e9944-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e9944-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e9944-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9944-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e9944-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e9944-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e9944-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e9944-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

