---
title: PidTagPstPathHint 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 9cb4af50-3735-4029-a608-a6e7927019dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6b71feb6d5967eab3aa490a256825a2803381f40
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569090"
---
# <a name="pidtagpstpathhint-canonical-property"></a><span data-ttu-id="51950-103">PidTagPstPathHint 规范属性</span><span class="sxs-lookup"><span data-stu-id="51950-103">PidTagPstPathHint Canonical Property</span></span>

  
  
<span data-ttu-id="51950-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="51950-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="51950-105">提供用于配置对话框的用户可以编辑的个人存储表 （.pst 文件） 名称。</span><span class="sxs-lookup"><span data-stu-id="51950-105">Provides the personal storage table (.pst file) name, which the user can edit, for the configuration dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="51950-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="51950-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="51950-107">PR_PST_PATH_HINT，PR_PST_PATH_HINT_A，PR_PST_PATH_HINT_W</span><span class="sxs-lookup"><span data-stu-id="51950-107">PR_PST_PATH_HINT, PR_PST_PATH_HINT_A, PR_PST_PATH_HINT_W</span></span>  <br/> |
|<span data-ttu-id="51950-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="51950-108">Identifier:</span></span>  <br/> |<span data-ttu-id="51950-109">0x6771</span><span class="sxs-lookup"><span data-stu-id="51950-109">0x6771</span></span>  <br/> |
|<span data-ttu-id="51950-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="51950-110">Data type:</span></span>  <br/> |<span data-ttu-id="51950-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="51950-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="51950-112">区域：</span><span class="sxs-lookup"><span data-stu-id="51950-112">Area:</span></span>  <br/> |<span data-ttu-id="51950-113">个人存储表 (.pst) 内部</span><span class="sxs-lookup"><span data-stu-id="51950-113">Personal storage table (.pst) internal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="51950-114">注解</span><span class="sxs-lookup"><span data-stu-id="51950-114">Remarks</span></span>

<span data-ttu-id="51950-115">如果改为使用**PR_PST_PATH** ([PidTagPstPath](pidtagpstpath-canonical-property.md)) 属性，则配置对话框将打开，但不是将允许用户编辑的路径和多个其他属性。</span><span class="sxs-lookup"><span data-stu-id="51950-115">If the **PR_PST_PATH** ([PidTagPstPath](pidtagpstpath-canonical-property.md)) property is used instead, the configuration dialog box will open, but the user will not be allowed to edit the path and many other properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="51950-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="51950-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="51950-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="51950-117">Protocol specifications</span></span>

<span data-ttu-id="51950-118">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="51950-118">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="51950-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="51950-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="51950-120">头文件</span><span class="sxs-lookup"><span data-stu-id="51950-120">Header files</span></span>

<span data-ttu-id="51950-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="51950-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="51950-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="51950-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="51950-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="51950-123">Mapitags.h</span></span>
  
> <span data-ttu-id="51950-124">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="51950-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51950-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51950-125">See also</span></span>



[<span data-ttu-id="51950-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="51950-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="51950-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="51950-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="51950-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="51950-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="51950-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="51950-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

