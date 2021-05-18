---
title: PidTagDefaultViewEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultViewEntryId
api_type:
- HeaderDef
ms.assetid: 1b4e82ed-c207-4828-8a5b-0ef312962355
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d284782de86b603e6bbe190931a85cd9196c88b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270012"
---
# <a name="pidtagdefaultviewentryid-canonical-property"></a><span data-ttu-id="adb06-103">PidTagDefaultViewEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="adb06-103">PidTagDefaultViewEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="adb06-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="adb06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="adb06-105">包含文件夹的默认视图的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="adb06-105">Contains the entry identifier of a folder's default view.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="adb06-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="adb06-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="adb06-107">PR_DEFAULT_VIEW_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="adb06-107">PR_DEFAULT_VIEW_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="adb06-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="adb06-108">Identifier:</span></span>  <br/> |<span data-ttu-id="adb06-109">0x3616</span><span class="sxs-lookup"><span data-stu-id="adb06-109">0x3616</span></span>  <br/> |
|<span data-ttu-id="adb06-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="adb06-110">Data type:</span></span>  <br/> |<span data-ttu-id="adb06-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="adb06-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="adb06-112">区域：</span><span class="sxs-lookup"><span data-stu-id="adb06-112">Area:</span></span>  <br/> |<span data-ttu-id="adb06-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="adb06-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="adb06-114">备注</span><span class="sxs-lookup"><span data-stu-id="adb06-114">Remarks</span></span>

<span data-ttu-id="adb06-115">此属性是应设置为初始视图的文件夹视图的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="adb06-115">This property is the entry identifier of the folder view that should be set as the initial view.</span></span> <span data-ttu-id="adb06-116">如果将"Normal"视图用作初始视图，则不需要设置该属性。</span><span class="sxs-lookup"><span data-stu-id="adb06-116">The property need not be set if the "Normal" view is to be used as the initial view.</span></span>
  
<span data-ttu-id="adb06-117">客户端应用程序可以在打开文件夹时获取此属性，并显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="adb06-117">A client application can obtain this property at the time it opens the folder and realize significant performance gains.</span></span> <span data-ttu-id="adb06-118">此属性可以用作获取默认视图的快捷方式，而不是打开关联的内容表并提交限制。</span><span class="sxs-lookup"><span data-stu-id="adb06-118">This property can be used as a shortcut to obtain the default view, instead of opening the associated contents table and submitting a restriction.</span></span>
  
<span data-ttu-id="adb06-119">[IMAPIFolder：：CopyFolder](imapifolder-copyfolder.md)方法的服务提供商实现可以在复制文件夹时复制此属性。</span><span class="sxs-lookup"><span data-stu-id="adb06-119">A service provider implementation of the [IMAPIFolder::CopyFolder](imapifolder-copyfolder.md) method can copy this property when it copies folders.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="adb06-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="adb06-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="adb06-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="adb06-121">Protocol specifications</span></span>

<span data-ttu-id="adb06-122">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="adb06-122">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="adb06-123">处理文件夹操作。</span><span class="sxs-lookup"><span data-stu-id="adb06-123">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="adb06-124">头文件</span><span class="sxs-lookup"><span data-stu-id="adb06-124">Header files</span></span>

<span data-ttu-id="adb06-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="adb06-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="adb06-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="adb06-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="adb06-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="adb06-127">Mapitags.h</span></span>
  
> <span data-ttu-id="adb06-128">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="adb06-128">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="adb06-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adb06-129">See also</span></span>



[<span data-ttu-id="adb06-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="adb06-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="adb06-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="adb06-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="adb06-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="adb06-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="adb06-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="adb06-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

