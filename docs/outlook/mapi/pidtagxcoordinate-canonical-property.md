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
ms.openlocfilehash: 3b5a4a337d8f92a3142aeb43eec9f2e9f0578a8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778568"
---
# <a name="pidtagxcoordinate-canonical-property"></a><span data-ttu-id="5fdb7-103">PidTagXCoordinate 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fdb7-103">PidTagXCoordinate Canonical Property</span></span>

  
  
<span data-ttu-id="5fdb7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5fdb7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5fdb7-105">包含的起始位置 （左上角） 对话框控件，以标准 Windows 对话框单位表示的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="5fdb7-105">Contains the x coordinate of the starting position (the upper-left corner) of a dialog box control, in standard Windows dialog units.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5fdb7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5fdb7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5fdb7-107">PR_XPOS</span><span class="sxs-lookup"><span data-stu-id="5fdb7-107">PR_XPOS</span></span>  <br/> |
|<span data-ttu-id="5fdb7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="5fdb7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5fdb7-109">0x3F05</span><span class="sxs-lookup"><span data-stu-id="5fdb7-109">0x3F05</span></span>  <br/> |
|<span data-ttu-id="5fdb7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5fdb7-110">Data type:</span></span>  <br/> |<span data-ttu-id="5fdb7-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5fdb7-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5fdb7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5fdb7-112">Area:</span></span>  <br/> |<span data-ttu-id="5fdb7-113">MAPI 显示表</span><span class="sxs-lookup"><span data-stu-id="5fdb7-113">MAPI display table</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5fdb7-114">说明</span><span class="sxs-lookup"><span data-stu-id="5fdb7-114">Remarks</span></span>

<span data-ttu-id="5fdb7-115">此属性、 **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md))、 **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)) 和**PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) 属性定位并调整大小对话框控件。</span><span class="sxs-lookup"><span data-stu-id="5fdb7-115">This property, **PR_YPOS** ([PidTagYCoordinate](pidtagycoordinate-canonical-property.md)), **PR_DELTAX** ([PidTagDeltaX](pidtagdeltax-canonical-property.md)), and **PR_DELTAY** ([PidTagDeltaY](pidtagdeltay-canonical-property.md)) properties position and size the dialog box control.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5fdb7-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="5fdb7-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="5fdb7-117">头文件</span><span class="sxs-lookup"><span data-stu-id="5fdb7-117">Header files</span></span>

<span data-ttu-id="5fdb7-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5fdb7-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="5fdb7-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5fdb7-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="5fdb7-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5fdb7-120">Mapitags.h</span></span>
  
> <span data-ttu-id="5fdb7-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5fdb7-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5fdb7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5fdb7-122">See also</span></span>



[<span data-ttu-id="5fdb7-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5fdb7-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5fdb7-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5fdb7-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5fdb7-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5fdb7-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5fdb7-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5fdb7-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

