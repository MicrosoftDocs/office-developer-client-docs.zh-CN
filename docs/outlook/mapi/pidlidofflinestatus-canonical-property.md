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
ms.openlocfilehash: 34f50766c2c45d85bbb0bd9e12d32c5dd87e3cac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776930"
---
# <a name="pidlidofflinestatus-canonical-property"></a><span data-ttu-id="8daa4-103">PidLidOfflineStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="8daa4-103">PidLidOfflineStatus Canonical Property</span></span>

  
  
<span data-ttu-id="8daa4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8daa4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8daa4-105">确定实现 [MS LISTSWS] 的服务器上的文档文件的状态。</span><span class="sxs-lookup"><span data-stu-id="8daa4-105">Determines the state of a document file on a server that implements [MS-LISTSWS].</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8daa4-106">相关的属性</span><span class="sxs-lookup"><span data-stu-id="8daa4-106">Associated properties</span></span>  <br/> |<span data-ttu-id="8daa4-107">dispidOfflineStatus</span><span class="sxs-lookup"><span data-stu-id="8daa4-107">dispidOfflineStatus</span></span>  <br/> |
|<span data-ttu-id="8daa4-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="8daa4-108">Property set:</span></span>  <br/> |<span data-ttu-id="8daa4-109">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="8daa4-109">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="8daa4-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="8daa4-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="8daa4-111">0x000085B9</span><span class="sxs-lookup"><span data-stu-id="8daa4-111">0x000085B9</span></span>  <br/> |
|<span data-ttu-id="8daa4-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8daa4-112">Data type:</span></span>  <br/> |<span data-ttu-id="8daa4-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8daa4-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8daa4-114">区域：</span><span class="sxs-lookup"><span data-stu-id="8daa4-114">Area:</span></span>  <br/> |<span data-ttu-id="8daa4-115">常规消息</span><span class="sxs-lookup"><span data-stu-id="8daa4-115">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8daa4-116">说明</span><span class="sxs-lookup"><span data-stu-id="8daa4-116">Remarks</span></span>

<span data-ttu-id="8daa4-117">下表显示了此属性的可能值。</span><span class="sxs-lookup"><span data-stu-id="8daa4-117">The following table shows the possible values of this property.</span></span>
  
|<span data-ttu-id="8daa4-118">**值**</span><span class="sxs-lookup"><span data-stu-id="8daa4-118">**Value**</span></span>|<span data-ttu-id="8daa4-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="8daa4-119">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8daa4-120">0</span><span class="sxs-lookup"><span data-stu-id="8daa4-120">0</span></span>  <br/> |<span data-ttu-id="8daa4-121">未签出文档。</span><span class="sxs-lookup"><span data-stu-id="8daa4-121">Document is not checked out.</span></span>  <br/> |
|<span data-ttu-id="8daa4-122">1</span><span class="sxs-lookup"><span data-stu-id="8daa4-122">1</span></span>  <br/> |<span data-ttu-id="8daa4-123">文档是当前用户签出。</span><span class="sxs-lookup"><span data-stu-id="8daa4-123">Document is checked out to the current user.</span></span>  <br/> |
|<span data-ttu-id="8daa4-124">2</span><span class="sxs-lookup"><span data-stu-id="8daa4-124">2</span></span>  <br/> |<span data-ttu-id="8daa4-125">文档未签出，但当前用户具有用于编辑当前计算机上保存的文件的副本。</span><span class="sxs-lookup"><span data-stu-id="8daa4-125">Document is not checked out, but the current user has a copy of the file saved for editing on the current computer.</span></span>  <br/> |
   
<span data-ttu-id="8daa4-126">此属性的本地计算并不会发送到服务器随时除非用户将项目拖动到另一个帐户。</span><span class="sxs-lookup"><span data-stu-id="8daa4-126">This property is calculated locally and is not sent to a server at any time unless a user drags the item to another account.</span></span> <span data-ttu-id="8daa4-127">在这种情况下，将其视为用户定义的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="8daa4-127">In that case, it is treated as a user-defined custom property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8daa4-128">相关资源</span><span class="sxs-lookup"><span data-stu-id="8daa4-128">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8daa4-129">协议规范</span><span class="sxs-lookup"><span data-stu-id="8daa4-129">Protocol specifications</span></span>

<span data-ttu-id="8daa4-130">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="8daa4-130">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="8daa4-131">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="8daa4-131">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8daa4-132">头文件</span><span class="sxs-lookup"><span data-stu-id="8daa4-132">Header files</span></span>

<span data-ttu-id="8daa4-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8daa4-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="8daa4-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8daa4-134">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8daa4-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8daa4-135">See also</span></span>



[<span data-ttu-id="8daa4-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8daa4-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8daa4-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8daa4-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8daa4-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8daa4-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8daa4-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8daa4-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

