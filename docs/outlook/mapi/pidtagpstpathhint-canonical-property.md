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
ms.openlocfilehash: 6415ddcec2823192967b8869b46b22b58b08ba5f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437306"
---
# <a name="pidtagpstpathhint-canonical-property"></a><span data-ttu-id="a3683-103">PidTagPstPathHint 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3683-103">PidTagPstPathHint Canonical Property</span></span>

  
  
<span data-ttu-id="a3683-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a3683-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a3683-105">为配置对话框 (.pst) 个人存储表，用户可以编辑该名称。</span><span class="sxs-lookup"><span data-stu-id="a3683-105">Provides the personal storage table (.pst file) name, which the user can edit, for the configuration dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a3683-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a3683-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a3683-107">PR_PST_PATH_HINT、PR_PST_PATH_HINT_A、PR_PST_PATH_HINT_W</span><span class="sxs-lookup"><span data-stu-id="a3683-107">PR_PST_PATH_HINT, PR_PST_PATH_HINT_A, PR_PST_PATH_HINT_W</span></span>  <br/> |
|<span data-ttu-id="a3683-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a3683-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a3683-109">0x6771</span><span class="sxs-lookup"><span data-stu-id="a3683-109">0x6771</span></span>  <br/> |
|<span data-ttu-id="a3683-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a3683-110">Data type:</span></span>  <br/> |<span data-ttu-id="a3683-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a3683-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a3683-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a3683-112">Area:</span></span>  <br/> |<span data-ttu-id="a3683-113">内部存储表 (.pst) 存储表</span><span class="sxs-lookup"><span data-stu-id="a3683-113">Personal storage table (.pst) internal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a3683-114">备注</span><span class="sxs-lookup"><span data-stu-id="a3683-114">Remarks</span></span>

<span data-ttu-id="a3683-115">如果 **PR_PST_PATH (** [PidTagPstPath](pidtagpstpath-canonical-property.md)) 属性，则配置对话框将打开，但不允许用户编辑路径和许多其他属性。</span><span class="sxs-lookup"><span data-stu-id="a3683-115">If the **PR_PST_PATH** ([PidTagPstPath](pidtagpstpath-canonical-property.md)) property is used instead, the configuration dialog box will open, but the user will not be allowed to edit the path and many other properties.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="a3683-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="a3683-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a3683-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="a3683-117">Protocol specifications</span></span>

<span data-ttu-id="a3683-118">[[MS-OXPROPS]]</span><span class="sxs-lookup"><span data-stu-id="a3683-118">[[MS-OXPROPS]]</span></span> 
  
> <span data-ttu-id="a3683-119">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="a3683-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a3683-120">头文件</span><span class="sxs-lookup"><span data-stu-id="a3683-120">Header files</span></span>

<span data-ttu-id="a3683-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a3683-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="a3683-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a3683-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="a3683-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a3683-123">Mapitags.h</span></span>
  
> <span data-ttu-id="a3683-124">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a3683-124">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a3683-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3683-125">See also</span></span>



[<span data-ttu-id="a3683-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a3683-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a3683-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a3683-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a3683-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a3683-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a3683-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a3683-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

