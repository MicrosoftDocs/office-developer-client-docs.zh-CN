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
ms.openlocfilehash: 5514e0553f719e2e875aad7001bb38a6a52e8e08
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589775"
---
# <a name="pidtagminiicon-canonical-property"></a><span data-ttu-id="07c4f-103">PidTagMiniIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="07c4f-103">PidTagMiniIcon Canonical Property</span></span>

  
  
<span data-ttu-id="07c4f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07c4f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07c4f-105">包含半尺寸图标的窗体的位图。</span><span class="sxs-lookup"><span data-stu-id="07c4f-105">Contains a bitmap of a half-size icon for a form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="07c4f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="07c4f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="07c4f-107">PR_MINI_ICON</span><span class="sxs-lookup"><span data-stu-id="07c4f-107">PR_MINI_ICON</span></span>  <br/> |
|<span data-ttu-id="07c4f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="07c4f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="07c4f-109">0x0FFC</span><span class="sxs-lookup"><span data-stu-id="07c4f-109">0x0FFC</span></span>  <br/> |
|<span data-ttu-id="07c4f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="07c4f-110">Data type:</span></span>  <br/> |<span data-ttu-id="07c4f-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="07c4f-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="07c4f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="07c4f-112">Area:</span></span>  <br/> |<span data-ttu-id="07c4f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="07c4f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="07c4f-114">注解</span><span class="sxs-lookup"><span data-stu-id="07c4f-114">Remarks</span></span>

<span data-ttu-id="07c4f-115">此属性包含一个图标，相同的内容的 32 × 32 像素图像。ICO 文件，但只有左上方 16x16 像素视为重要。</span><span class="sxs-lookup"><span data-stu-id="07c4f-115">This property contains a 32 × 32 pixel image of an icon, the same as the contents of a .ICO file, but only the upper left 16 × 16 pixels are considered significant.</span></span> <span data-ttu-id="07c4f-116">此属性通常从复制。ICO SmallIcon 行的窗体配置文件的适当 [描述] 节中指定的文件。</span><span class="sxs-lookup"><span data-stu-id="07c4f-116">This property is normally copied from the .ICO file specified in the SmallIcon line of the appropriate [Description] section of the form configuration file.</span></span>
  
 <span data-ttu-id="07c4f-117">**注释**某些平台执行不支持 16x16 像素的图标。</span><span class="sxs-lookup"><span data-stu-id="07c4f-117">**Note** Some platforms do not support 16 × 16 pixel icons.</span></span> <span data-ttu-id="07c4f-118">此属性的 32 × 32 格式是这种情况下可用，但客户端应用程序应注意的显示不一致。</span><span class="sxs-lookup"><span data-stu-id="07c4f-118">The 32 × 32 format of this property is usable in such a case but client applications should be aware of display inconsistencies.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="07c4f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="07c4f-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="07c4f-120">头文件</span><span class="sxs-lookup"><span data-stu-id="07c4f-120">Header files</span></span>

<span data-ttu-id="07c4f-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="07c4f-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="07c4f-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="07c4f-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="07c4f-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="07c4f-123">Mapitags.h</span></span>
  
> <span data-ttu-id="07c4f-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="07c4f-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="07c4f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07c4f-125">See also</span></span>



[<span data-ttu-id="07c4f-126">PidTagIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="07c4f-126">PidTagIcon Canonical Property</span></span>](pidtagicon-canonical-property.md)


[<span data-ttu-id="07c4f-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="07c4f-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="07c4f-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="07c4f-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="07c4f-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="07c4f-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="07c4f-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="07c4f-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

