---
title: PidTagRenderingPosition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRenderingPosition
api_type:
- COM
ms.assetid: bce46687-17dc-4a3f-96be-303d8755158e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d463be4a14ecf478bdcbddc50b4ad9360829befc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355151"
---
# <a name="pidtagrenderingposition-canonical-property"></a><span data-ttu-id="c6132-103">PidTagRenderingPosition 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6132-103">PidTagRenderingPosition Canonical Property</span></span>

  
  
<span data-ttu-id="c6132-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c6132-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c6132-105">包含在主邮件文本中呈现附件时要使用的偏移量 (以字符为单位)。</span><span class="sxs-lookup"><span data-stu-id="c6132-105">Contains an offset, in characters, to use in rendering an attachment within the main message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c6132-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c6132-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c6132-107">PR_RENDERING_POSITION</span><span class="sxs-lookup"><span data-stu-id="c6132-107">PR_RENDERING_POSITION</span></span>  <br/> |
|<span data-ttu-id="c6132-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c6132-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c6132-109">0x370B</span><span class="sxs-lookup"><span data-stu-id="c6132-109">0x370B</span></span>  <br/> |
|<span data-ttu-id="c6132-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c6132-110">Data type:</span></span>  <br/> |<span data-ttu-id="c6132-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c6132-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c6132-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c6132-112">Area:</span></span>  <br/> |<span data-ttu-id="c6132-113">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="c6132-113">MAPI attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c6132-114">注解</span><span class="sxs-lookup"><span data-stu-id="c6132-114">Remarks</span></span>

<span data-ttu-id="c6132-115">当提供的偏移量为-1 (0xffffffff) 时, 不使用此属性呈现附件。</span><span class="sxs-lookup"><span data-stu-id="c6132-115">When the supplied offset is -1 (0xFFFFFFFF), the attachment is not rendered by using this property.</span></span> <span data-ttu-id="c6132-116">-1 以外的所有值指示要在**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中呈现附件的位置。</span><span class="sxs-lookup"><span data-stu-id="c6132-116">All values other than -1 indicate the position within the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property at which the attachment is to be rendered.</span></span>
  
 <span data-ttu-id="c6132-117">**注释**由**PR_BODY**中的此属性指示的字符将替换为附件。</span><span class="sxs-lookup"><span data-stu-id="c6132-117">**Note** The character indicated by this property in **PR_BODY** is replaced by the attachment.</span></span> <span data-ttu-id="c6132-118">通常, 此字符是一个空格, 尽管也可以使用一个特殊的占位符字符。</span><span class="sxs-lookup"><span data-stu-id="c6132-118">Typically this character is a space, although a special placeholder character can also be used.</span></span> 
  
<span data-ttu-id="c6132-119">此属性以字符表示。</span><span class="sxs-lookup"><span data-stu-id="c6132-119">This property is expressed in characters.</span></span> <span data-ttu-id="c6132-120">在某些字符集中, 这与字节不等效。</span><span class="sxs-lookup"><span data-stu-id="c6132-120">In some character sets this is not equivalent to bytes.</span></span> <span data-ttu-id="c6132-121">Unicode 应用程序可以基于双字节字符计算位置。</span><span class="sxs-lookup"><span data-stu-id="c6132-121">Unicode applications can compute the position based on two-byte characters.</span></span> <span data-ttu-id="c6132-122">双字节字符集 (DBCS) 应用程序必须将文本扫描到此属性值, 因为它们的字符表示形式在每个字符的1到2个字节之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="c6132-122">Double-Byte Character Set (DBCS) applications must scan the text up to this property value, because their character representation varies between one and two bytes per character.</span></span>
  
<span data-ttu-id="c6132-123">此属性不应用于 rtf 格式文本。</span><span class="sxs-lookup"><span data-stu-id="c6132-123">This property should not be used with Rich Text Format (RTF) text.</span></span> <span data-ttu-id="c6132-124">呈现位置通过称为对象附件占位符的转义序列以 RTF 表示。</span><span class="sxs-lookup"><span data-stu-id="c6132-124">The rendering position is indicated in RTF by an escape sequence called the object attachment placeholder.</span></span> <span data-ttu-id="c6132-125">此序列由后跟单个`\objattph`字符 (通常为空格) 的字符串组成, 附件呈现将替换该字符串。</span><span class="sxs-lookup"><span data-stu-id="c6132-125">This sequence consists of the string  `\objattph` followed by a single character, normally a space, that will be replaced by the attachment rendering.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c6132-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="c6132-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c6132-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="c6132-127">Protocol specifications</span></span>

<span data-ttu-id="c6132-128">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c6132-128">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c6132-129">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c6132-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c6132-130">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c6132-130">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c6132-131">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="c6132-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c6132-132">头文件</span><span class="sxs-lookup"><span data-stu-id="c6132-132">Header files</span></span>

<span data-ttu-id="c6132-133">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c6132-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="c6132-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c6132-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="c6132-135">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c6132-135">Mapitags.h</span></span>
  
> <span data-ttu-id="c6132-136">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c6132-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c6132-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6132-137">See also</span></span>



[<span data-ttu-id="c6132-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c6132-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c6132-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c6132-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c6132-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c6132-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c6132-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c6132-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

