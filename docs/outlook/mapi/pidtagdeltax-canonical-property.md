---
title: PidTagDeltaX 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeltaX
api_type:
- HeaderDef
ms.assetid: 9bbe996b-1cfc-46d7-bb0a-291c760500ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efaca709b666458b0cd2f2de2124fa900d2a75b4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420519"
---
# <a name="pidtagdeltax-canonical-property"></a><span data-ttu-id="7f2a0-103">PidTagDeltaX 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f2a0-103">PidTagDeltaX Canonical Property</span></span>

  
  
<span data-ttu-id="7f2a0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7f2a0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7f2a0-105">包含以标准对话框单位表示的对话框Windows的宽度。</span><span class="sxs-lookup"><span data-stu-id="7f2a0-105">Contains the width of a dialog box control in standard Windows dialog units.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7f2a0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7f2a0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7f2a0-107">PR_DELTAX</span><span class="sxs-lookup"><span data-stu-id="7f2a0-107">PR_DELTAX</span></span>  <br/> |
|<span data-ttu-id="7f2a0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7f2a0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7f2a0-109">0x3F03</span><span class="sxs-lookup"><span data-stu-id="7f2a0-109">0x3F03</span></span>  <br/> |
|<span data-ttu-id="7f2a0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7f2a0-110">Data type:</span></span>  <br/> |<span data-ttu-id="7f2a0-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7f2a0-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7f2a0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7f2a0-112">Area:</span></span>  <br/> |<span data-ttu-id="7f2a0-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="7f2a0-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7f2a0-114">备注</span><span class="sxs-lookup"><span data-stu-id="7f2a0-114">Remarks</span></span>

<span data-ttu-id="7f2a0-115">PR_XPOS  ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md) **) 、PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md) **) 、PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性，此属性控制对话框控件的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="7f2a0-115">The **PR_XPOS** ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md)), **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md)), **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) properties ,and this property control the position and size the dialog box control.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7f2a0-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="7f2a0-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="7f2a0-117">头文件</span><span class="sxs-lookup"><span data-stu-id="7f2a0-117">Header files</span></span>

<span data-ttu-id="7f2a0-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7f2a0-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="7f2a0-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7f2a0-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="7f2a0-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7f2a0-120">Mapitags.h</span></span>
  
> <span data-ttu-id="7f2a0-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7f2a0-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7f2a0-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f2a0-122">See also</span></span>



[<span data-ttu-id="7f2a0-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7f2a0-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7f2a0-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f2a0-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7f2a0-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7f2a0-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7f2a0-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7f2a0-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

