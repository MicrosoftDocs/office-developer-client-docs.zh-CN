---
title: PidLidOfflineStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOfflineStatus
api_type:
- COM
ms.assetid: ee69f0c4-b552-4cfd-8a39-a822d414549e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 537b45420390903d67722c074a1edcc04a0aede8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418832"
---
# <a name="pidlidofflinestatus-canonical-property"></a><span data-ttu-id="2ece4-103">PidLidOfflineStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ece4-103">PidLidOfflineStatus Canonical Property</span></span>

  
  
<span data-ttu-id="2ece4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ece4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ece4-105">确定实现 [MS-LISTSWS] 的服务器上文档文件的状态。</span><span class="sxs-lookup"><span data-stu-id="2ece4-105">Determines the state of a document file on a server that implements [MS-LISTSWS].</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ece4-106">关联的属性</span><span class="sxs-lookup"><span data-stu-id="2ece4-106">Associated properties</span></span>  <br/> |<span data-ttu-id="2ece4-107">dispidOfflineStatus</span><span class="sxs-lookup"><span data-stu-id="2ece4-107">dispidOfflineStatus</span></span>  <br/> |
|<span data-ttu-id="2ece4-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="2ece4-108">Property set:</span></span>  <br/> |<span data-ttu-id="2ece4-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2ece4-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2ece4-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="2ece4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2ece4-111">0x000085B9</span><span class="sxs-lookup"><span data-stu-id="2ece4-111">0x000085B9</span></span>  <br/> |
|<span data-ttu-id="2ece4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ece4-112">Data type:</span></span>  <br/> |<span data-ttu-id="2ece4-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2ece4-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2ece4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2ece4-114">Area:</span></span>  <br/> |<span data-ttu-id="2ece4-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="2ece4-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ece4-116">备注</span><span class="sxs-lookup"><span data-stu-id="2ece4-116">Remarks</span></span>

<span data-ttu-id="2ece4-117">下表显示了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="2ece4-117">The following table shows the possible values of this property.</span></span>
  
|<span data-ttu-id="2ece4-118">**值**</span><span class="sxs-lookup"><span data-stu-id="2ece4-118">**Value**</span></span>|<span data-ttu-id="2ece4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="2ece4-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2ece4-120">0</span><span class="sxs-lookup"><span data-stu-id="2ece4-120">0</span></span>  <br/> |<span data-ttu-id="2ece4-121">文档未签出。</span><span class="sxs-lookup"><span data-stu-id="2ece4-121">Document is not checked out.</span></span>  <br/> |
|<span data-ttu-id="2ece4-122">1</span><span class="sxs-lookup"><span data-stu-id="2ece4-122">1</span></span>  <br/> |<span data-ttu-id="2ece4-123">文档已签出给当前用户。</span><span class="sxs-lookup"><span data-stu-id="2ece4-123">Document is checked out to the current user.</span></span>  <br/> |
|<span data-ttu-id="2ece4-124">2</span><span class="sxs-lookup"><span data-stu-id="2ece4-124">2</span></span>  <br/> |<span data-ttu-id="2ece4-125">文档未签出，但当前用户具有保存在当前计算机上进行编辑的文件的副本。</span><span class="sxs-lookup"><span data-stu-id="2ece4-125">Document is not checked out, but the current user has a copy of the file saved for editing on the current computer.</span></span>  <br/> |
   
<span data-ttu-id="2ece4-126">此属性在本地计算，并且不会随时发送到服务器，除非用户将项目拖动到另一个帐户。</span><span class="sxs-lookup"><span data-stu-id="2ece4-126">This property is calculated locally and is not sent to a server at any time unless a user drags the item to another account.</span></span> <span data-ttu-id="2ece4-127">在这种情况下，它将被视为用户定义的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="2ece4-127">In that case, it is treated as a user-defined custom property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2ece4-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="2ece4-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2ece4-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="2ece4-129">Protocol specifications</span></span>

<span data-ttu-id="2ece4-130">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="2ece4-130">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="2ece4-131">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="2ece4-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2ece4-132">头文件</span><span class="sxs-lookup"><span data-stu-id="2ece4-132">Header files</span></span>

<span data-ttu-id="2ece4-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2ece4-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="2ece4-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2ece4-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ece4-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ece4-135">See also</span></span>



[<span data-ttu-id="2ece4-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ece4-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ece4-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ece4-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ece4-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ece4-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ece4-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ece4-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

