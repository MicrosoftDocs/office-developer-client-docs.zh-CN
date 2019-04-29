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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea7f9e0ed57c56b48399b9ffd1ea42db28daf249
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405413"
---
# <a name="pidtagminiicon-canonical-property"></a><span data-ttu-id="85ebd-103">PidTagMiniIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="85ebd-103">PidTagMiniIcon Canonical Property</span></span>

  
  
<span data-ttu-id="85ebd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85ebd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85ebd-105">包含窗体的半尺寸图标的位图。</span><span class="sxs-lookup"><span data-stu-id="85ebd-105">Contains a bitmap of a half-size icon for a form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="85ebd-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="85ebd-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="85ebd-107">PR_MINI_ICON</span><span class="sxs-lookup"><span data-stu-id="85ebd-107">PR_MINI_ICON</span></span>  <br/> |
|<span data-ttu-id="85ebd-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="85ebd-108">Identifier:</span></span>  <br/> |<span data-ttu-id="85ebd-109">0x0FFC</span><span class="sxs-lookup"><span data-stu-id="85ebd-109">0x0FFC</span></span>  <br/> |
|<span data-ttu-id="85ebd-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="85ebd-110">Data type:</span></span>  <br/> |<span data-ttu-id="85ebd-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="85ebd-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="85ebd-112">区域：</span><span class="sxs-lookup"><span data-stu-id="85ebd-112">Area:</span></span>  <br/> |<span data-ttu-id="85ebd-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="85ebd-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="85ebd-114">说明</span><span class="sxs-lookup"><span data-stu-id="85ebd-114">Remarks</span></span>

<span data-ttu-id="85ebd-115">此属性包含一个图标的32×32像素的图像, 其内容与 a 的内容相同。.ico 文件, 但只有左上的16×16像素被视为有效。</span><span class="sxs-lookup"><span data-stu-id="85ebd-115">This property contains a 32 × 32 pixel image of an icon, the same as the contents of a .ICO file, but only the upper left 16 × 16 pixels are considered significant.</span></span> <span data-ttu-id="85ebd-116">此属性通常是从复制的。在表单配置文件的相应 [Description] 部分的 SmallIcon 行中指定的 .ico 文件。</span><span class="sxs-lookup"><span data-stu-id="85ebd-116">This property is normally copied from the .ICO file specified in the SmallIcon line of the appropriate [Description] section of the form configuration file.</span></span>
  
 <span data-ttu-id="85ebd-117">**注释**有些平台不支持16×16像素图标。</span><span class="sxs-lookup"><span data-stu-id="85ebd-117">**Note** Some platforms do not support 16 × 16 pixel icons.</span></span> <span data-ttu-id="85ebd-118">此属性的32×32格式在这种情况下可用, 但客户端应用程序应了解显示不一致。</span><span class="sxs-lookup"><span data-stu-id="85ebd-118">The 32 × 32 format of this property is usable in such a case but client applications should be aware of display inconsistencies.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="85ebd-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="85ebd-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="85ebd-120">头文件</span><span class="sxs-lookup"><span data-stu-id="85ebd-120">Header files</span></span>

<span data-ttu-id="85ebd-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="85ebd-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="85ebd-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="85ebd-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="85ebd-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="85ebd-123">Mapitags.h</span></span>
  
> <span data-ttu-id="85ebd-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="85ebd-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="85ebd-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85ebd-125">See also</span></span>



[<span data-ttu-id="85ebd-126">PidTagIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="85ebd-126">PidTagIcon Canonical Property</span></span>](pidtagicon-canonical-property.md)


[<span data-ttu-id="85ebd-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="85ebd-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="85ebd-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="85ebd-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="85ebd-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="85ebd-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="85ebd-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="85ebd-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

