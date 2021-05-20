---
title: PidTagXCoordinate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagXCoordinate
api_type:
- COM
ms.assetid: 030d5c21-ab02-4047-bf2d-9a402a1e9102
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87df676dccdb067302d62da2bd1fda6b634ed4f8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436193"
---
# <a name="pidtagxcoordinate-canonical-property"></a><span data-ttu-id="3ae90-103">PidTagXCoordinate 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ae90-103">PidTagXCoordinate Canonical Property</span></span>

  
  
<span data-ttu-id="3ae90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ae90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3ae90-105">包含对话框控件左上角 (位置的 x 坐标) ，以标准对话框Windows表示。</span><span class="sxs-lookup"><span data-stu-id="3ae90-105">Contains the x coordinate of the starting position (the upper-left corner) of a dialog box control, in standard Windows dialog units.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3ae90-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3ae90-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3ae90-107">PR_XPOS</span><span class="sxs-lookup"><span data-stu-id="3ae90-107">PR_XPOS</span></span>  <br/> |
|<span data-ttu-id="3ae90-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3ae90-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3ae90-109">0x3F05</span><span class="sxs-lookup"><span data-stu-id="3ae90-109">0x3F05</span></span>  <br/> |
|<span data-ttu-id="3ae90-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ae90-110">Data type:</span></span>  <br/> |<span data-ttu-id="3ae90-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3ae90-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3ae90-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3ae90-112">Area:</span></span>  <br/> |<span data-ttu-id="3ae90-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="3ae90-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ae90-114">备注</span><span class="sxs-lookup"><span data-stu-id="3ae90-114">Remarks</span></span>

<span data-ttu-id="3ae90-115">此属性 **、PR_YPOS (** [PidTagYCoordinate](pidtagycoordinate-canonical-property.md)) 、PR_DELTAX ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和 **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性位置和调整对话框控件的大小。 </span><span class="sxs-lookup"><span data-stu-id="3ae90-115">This property, **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md)), **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)), and **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) properties position and size the dialog box control.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3ae90-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="3ae90-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3ae90-117">头文件</span><span class="sxs-lookup"><span data-stu-id="3ae90-117">Header files</span></span>

<span data-ttu-id="3ae90-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3ae90-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="3ae90-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3ae90-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="3ae90-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3ae90-120">Mapitags.h</span></span>
  
> <span data-ttu-id="3ae90-121">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3ae90-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ae90-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ae90-122">See also</span></span>



[<span data-ttu-id="3ae90-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3ae90-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3ae90-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ae90-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3ae90-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3ae90-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3ae90-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3ae90-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

