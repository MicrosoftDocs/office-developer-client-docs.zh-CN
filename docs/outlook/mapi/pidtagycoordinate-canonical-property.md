---
title: PidTagYCoordinate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagYCoordinate
api_type:
- COM
ms.assetid: f176308d-efb9-460c-8379-8a12d4f8e017
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ab90b05f8bd92f4cfd90f84078691a293ae159b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350664"
---
# <a name="pidtagycoordinate-canonical-property"></a><span data-ttu-id="c9802-103">PidTagYCoordinate 规范属性</span><span class="sxs-lookup"><span data-stu-id="c9802-103">PidTagYCoordinate Canonical Property</span></span>

  
  
<span data-ttu-id="c9802-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c9802-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c9802-105">包含对话框控件的起始位置 (左上角) 的 y 坐标 (采用标准 Windows 对话框的单位)。</span><span class="sxs-lookup"><span data-stu-id="c9802-105">Contains the y coordinate of the starting position (the upper-left corner) of a dialog box control, in standard Windows dialog units.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c9802-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c9802-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c9802-107">PR_YPOS</span><span class="sxs-lookup"><span data-stu-id="c9802-107">PR_YPOS</span></span>  <br/> |
|<span data-ttu-id="c9802-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c9802-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c9802-109">0x3F06</span><span class="sxs-lookup"><span data-stu-id="c9802-109">0x3F06</span></span>  <br/> |
|<span data-ttu-id="c9802-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c9802-110">Data type:</span></span>  <br/> |<span data-ttu-id="c9802-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c9802-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c9802-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c9802-112">Area:</span></span>  <br/> |<span data-ttu-id="c9802-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="c9802-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c9802-114">注解</span><span class="sxs-lookup"><span data-stu-id="c9802-114">Remarks</span></span>

<span data-ttu-id="c9802-115">**PR_XPOS** ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md))、此属性、 **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和**PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性定位并调整控件的大小。</span><span class="sxs-lookup"><span data-stu-id="c9802-115">The **PR_XPOS** ([PidTagXCoordinate](pidtagxcoordinate-canonical-property.md)), this property, **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)), and **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) properties position and size the control.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c9802-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="c9802-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="c9802-117">头文件</span><span class="sxs-lookup"><span data-stu-id="c9802-117">Header files</span></span>

<span data-ttu-id="c9802-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c9802-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="c9802-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c9802-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="c9802-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c9802-120">Mapitags.h</span></span>
  
> <span data-ttu-id="c9802-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c9802-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c9802-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9802-122">See also</span></span>



[<span data-ttu-id="c9802-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c9802-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c9802-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c9802-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c9802-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c9802-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c9802-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c9802-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

