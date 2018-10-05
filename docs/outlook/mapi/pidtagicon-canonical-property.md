---
title: PidTagIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIcon
api_type:
- HeaderDef
ms.assetid: 815dabf3-3cac-40e1-b6ff-51db2ff5096a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ad8d6934b5e57429de5039e9420742caa9dd4294
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397693"
---
# <a name="pidtagicon-canonical-property"></a><span data-ttu-id="149f1-103">PidTagIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="149f1-103">PidTagIcon Canonical Property</span></span>

  
  
<span data-ttu-id="149f1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="149f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="149f1-105">包含窗体的完整大小的图标的位图。</span><span class="sxs-lookup"><span data-stu-id="149f1-105">Contains a bitmap of a full size icon for a form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="149f1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="149f1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="149f1-107">PR_ICON</span><span class="sxs-lookup"><span data-stu-id="149f1-107">PR_ICON</span></span>  <br/> |
|<span data-ttu-id="149f1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="149f1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="149f1-109">0x0FFD</span><span class="sxs-lookup"><span data-stu-id="149f1-109">0x0FFD</span></span>  <br/> |
|<span data-ttu-id="149f1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="149f1-110">Data type:</span></span>  <br/> |<span data-ttu-id="149f1-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="149f1-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="149f1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="149f1-112">Area:</span></span>  <br/> |<span data-ttu-id="149f1-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="149f1-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="149f1-114">说明</span><span class="sxs-lookup"><span data-stu-id="149f1-114">Remarks</span></span>

<span data-ttu-id="149f1-115">此属性包含一个图标，相同的内容的 32 × 32 像素图像。ICO 文件。</span><span class="sxs-lookup"><span data-stu-id="149f1-115">This property contains a 32 × 32 pixel image of an icon, the same as the contents of a .ICO file.</span></span> <span data-ttu-id="149f1-116">此属性通常从复制。ICO 文件指定相应的窗体配置文件的 [描述] 部分的视图行中。</span><span class="sxs-lookup"><span data-stu-id="149f1-116">This property is normally copied from the .ICO file specified in the LargeIcon line of the appropriate [Description] section of the form configuration file.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="149f1-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="149f1-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="149f1-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="149f1-118">Protocol specifications</span></span>

<span data-ttu-id="149f1-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="149f1-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="149f1-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="149f1-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="149f1-121">头文件</span><span class="sxs-lookup"><span data-stu-id="149f1-121">Header files</span></span>

<span data-ttu-id="149f1-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="149f1-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="149f1-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="149f1-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="149f1-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="149f1-124">Mapitags.h</span></span>
  
> <span data-ttu-id="149f1-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="149f1-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="149f1-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="149f1-126">See also</span></span>



[<span data-ttu-id="149f1-127">PidTagMiniIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="149f1-127">PidTagMiniIcon Canonical Property</span></span>](pidtagminiicon-canonical-property.md)


[<span data-ttu-id="149f1-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="149f1-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="149f1-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="149f1-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="149f1-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="149f1-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="149f1-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="149f1-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

