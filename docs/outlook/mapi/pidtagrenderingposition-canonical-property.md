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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: aa149a81102a4981712ea3ca897d8b1ad448a1eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778201"
---
# <a name="pidtagrenderingposition-canonical-property"></a><span data-ttu-id="5d4ba-103">PidTagRenderingPosition 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d4ba-103">PidTagRenderingPosition Canonical Property</span></span>

  
  
<span data-ttu-id="5d4ba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5d4ba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5d4ba-105">包含偏移量，以字符，用于在呈现主消息文本中的附件。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-105">Contains an offset, in characters, to use in rendering an attachment within the main message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d4ba-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="5d4ba-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5d4ba-107">PR_RENDERING_POSITION</span><span class="sxs-lookup"><span data-stu-id="5d4ba-107">PR_RENDERING_POSITION</span></span>  <br/> |
|<span data-ttu-id="5d4ba-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5d4ba-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5d4ba-109">0x370B</span><span class="sxs-lookup"><span data-stu-id="5d4ba-109">0x370B</span></span>  <br/> |
|<span data-ttu-id="5d4ba-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5d4ba-110">Data type:</span></span>  <br/> |<span data-ttu-id="5d4ba-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5d4ba-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5d4ba-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5d4ba-112">Area:</span></span>  <br/> |<span data-ttu-id="5d4ba-113">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="5d4ba-113">MAPI attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5d4ba-114">备注</span><span class="sxs-lookup"><span data-stu-id="5d4ba-114">Remarks</span></span>

<span data-ttu-id="5d4ba-115">时提供的偏移量为-1 (0xFFFFFFFF)，则不使用此属性中呈现附件。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-115">When the supplied offset is -1 (0xFFFFFFFF), the attachment is not rendered by using this property.</span></span> <span data-ttu-id="5d4ba-116">-1 以外的所有值都指示频率附件是要呈现的**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性中的位置。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-116">All values other than -1 indicate the position within the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property at which the attachment is to be rendered.</span></span>
  
 <span data-ttu-id="5d4ba-117">**注释**附件被替换**PR_BODY**中此属性指定的字符。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-117">**Note** The character indicated by this property in **PR_BODY** is replaced by the attachment.</span></span> <span data-ttu-id="5d4ba-118">通常该字符为一个空格，但也可以使用特殊的占位符。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-118">Typically this character is a space, although a special placeholder character can also be used.</span></span> 
  
<span data-ttu-id="5d4ba-119">此属性以字符为单位。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-119">This property is expressed in characters.</span></span> <span data-ttu-id="5d4ba-120">在某些字符集这是不等于字节。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-120">In some character sets this is not equivalent to bytes.</span></span> <span data-ttu-id="5d4ba-121">Unicode 应用程序可以计算基于双字节字符的位置。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-121">Unicode applications can compute the position based on two-byte characters.</span></span> <span data-ttu-id="5d4ba-122">双字节字符集 (DBCS) 应用程序必须扫描的文本，最多为此属性值，因为其字符表示形式而异每个字符的一和第二个字节。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-122">Double-Byte Character Set (DBCS) applications must scan the text up to this property value, because their character representation varies between one and two bytes per character.</span></span>
  
<span data-ttu-id="5d4ba-123">使用富文本格式 (RTF) 文本，不应使用此属性。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-123">This property should not be used with Rich Text Format (RTF) text.</span></span> <span data-ttu-id="5d4ba-124">呈现位置的转义序列调用对象的附件占位符指示以 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-124">The rendering position is indicated in RTF by an escape sequence called the object attachment placeholder.</span></span> <span data-ttu-id="5d4ba-125">此序列包含字符串`\objattph`跟单个字符，通常空格将替换为附件呈现。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-125">This sequence consists of the string  `\objattph` followed by a single character, normally a space, that will be replaced by the attachment rendering.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="5d4ba-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="5d4ba-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5d4ba-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="5d4ba-127">Protocol specifications</span></span>

<span data-ttu-id="5d4ba-128">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d4ba-128">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d4ba-129">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-129">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5d4ba-130">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d4ba-130">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5d4ba-131">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-131">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5d4ba-132">头文件</span><span class="sxs-lookup"><span data-stu-id="5d4ba-132">Header files</span></span>

<span data-ttu-id="5d4ba-133">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5d4ba-133">Mapidefs.h</span></span>
  
> <span data-ttu-id="5d4ba-134">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-134">Provides data type definitions.</span></span>
    
<span data-ttu-id="5d4ba-135">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5d4ba-135">Mapitags.h</span></span>
  
> <span data-ttu-id="5d4ba-136">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5d4ba-136">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5d4ba-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4ba-137">See also</span></span>



[<span data-ttu-id="5d4ba-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5d4ba-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5d4ba-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5d4ba-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5d4ba-140">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d4ba-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5d4ba-141">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5d4ba-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

