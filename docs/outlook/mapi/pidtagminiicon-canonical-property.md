---
title: PidTagMiniIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMiniIcon
api_type:
- HeaderDef
ms.assetid: a436b590-63f3-413c-a9c2-7664567e0ff0
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 04d78bddc7bae27ba23cccf676eb6e7412ffc0db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777875"
---
# <a name="pidtagminiicon-canonical-property"></a><span data-ttu-id="19fb5-103">PidTagMiniIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="19fb5-103">PidTagMiniIcon Canonical Property</span></span>

  
  
<span data-ttu-id="19fb5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19fb5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19fb5-105">包含半尺寸图标的窗体的位图。</span><span class="sxs-lookup"><span data-stu-id="19fb5-105">Contains a bitmap of a half-size icon for a form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="19fb5-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="19fb5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="19fb5-107">PR_MINI_ICON</span><span class="sxs-lookup"><span data-stu-id="19fb5-107">PR_MINI_ICON</span></span>  <br/> |
|<span data-ttu-id="19fb5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="19fb5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="19fb5-109">0x0FFC</span><span class="sxs-lookup"><span data-stu-id="19fb5-109">0x0FFC</span></span>  <br/> |
|<span data-ttu-id="19fb5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="19fb5-110">Data type:</span></span>  <br/> |<span data-ttu-id="19fb5-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="19fb5-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="19fb5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="19fb5-112">Area:</span></span>  <br/> |<span data-ttu-id="19fb5-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="19fb5-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="19fb5-114">备注</span><span class="sxs-lookup"><span data-stu-id="19fb5-114">Remarks</span></span>

<span data-ttu-id="19fb5-115">此属性包含一个图标，相同的内容的 32 × 32 像素图像。ICO 文件，但只有左上方 16x16 像素视为重要。</span><span class="sxs-lookup"><span data-stu-id="19fb5-115">This property contains a 32 × 32 pixel image of an icon, the same as the contents of a .ICO file, but only the upper left 16 × 16 pixels are considered significant.</span></span> <span data-ttu-id="19fb5-116">此属性通常从复制。ICO SmallIcon 行的窗体配置文件的适当 [描述] 节中指定的文件。</span><span class="sxs-lookup"><span data-stu-id="19fb5-116">This property is normally copied from the .ICO file specified in the SmallIcon line of the appropriate [Description] section of the form configuration file.</span></span>
  
 <span data-ttu-id="19fb5-117">**注释**某些平台执行不支持 16x16 像素的图标。</span><span class="sxs-lookup"><span data-stu-id="19fb5-117">**Note** Some platforms do not support 16 × 16 pixel icons.</span></span> <span data-ttu-id="19fb5-118">此属性的 32 × 32 格式是这种情况下可用，但客户端应用程序应注意的显示不一致。</span><span class="sxs-lookup"><span data-stu-id="19fb5-118">The 32 × 32 format of this property is usable in such a case but client applications should be aware of display inconsistencies.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="19fb5-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="19fb5-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="19fb5-120">头文件</span><span class="sxs-lookup"><span data-stu-id="19fb5-120">Header files</span></span>

<span data-ttu-id="19fb5-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="19fb5-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="19fb5-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="19fb5-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="19fb5-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="19fb5-123">Mapitags.h</span></span>
  
> <span data-ttu-id="19fb5-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="19fb5-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19fb5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19fb5-125">See also</span></span>



[<span data-ttu-id="19fb5-126">PidTagIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="19fb5-126">PidTagIcon Canonical Property</span></span>](pidtagicon-canonical-property.md)


[<span data-ttu-id="19fb5-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="19fb5-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="19fb5-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="19fb5-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="19fb5-129">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19fb5-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="19fb5-130">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19fb5-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

