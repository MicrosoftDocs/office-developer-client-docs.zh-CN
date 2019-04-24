---
title: PidTagOriginalSensitivity 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSensitivity
api_type:
- COM
ms.assetid: 70a87cf8-2011-4669-90fd-2711c3352e30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e712a4cc49541ee4330f479d7a03af323bdbc887
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341228"
---
# <a name="pidtagoriginalsensitivity-canonical-property"></a><span data-ttu-id="c053f-103">PidTagOriginalSensitivity 规范属性</span><span class="sxs-lookup"><span data-stu-id="c053f-103">PidTagOriginalSensitivity Canonical Property</span></span>

  
  
<span data-ttu-id="c053f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c053f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c053f-105">包含邮件的第一种版本的发件人分配的敏感度值, 即邮件转发或答复前的邮件。</span><span class="sxs-lookup"><span data-stu-id="c053f-105">Contains the sensitivity value assigned by the sender of the first version of a message that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c053f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c053f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c053f-107">PR_ORIGINAL_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="c053f-107">PR_ORIGINAL_SENSITIVITY</span></span>  <br/> |
|<span data-ttu-id="c053f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="c053f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c053f-109">0x002E</span><span class="sxs-lookup"><span data-stu-id="c053f-109">0x002E</span></span>  <br/> |
|<span data-ttu-id="c053f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c053f-110">Data type:</span></span>  <br/> |<span data-ttu-id="c053f-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="c053f-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="c053f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c053f-112">Area:</span></span>  <br/> |<span data-ttu-id="c053f-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="c053f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c053f-114">注解</span><span class="sxs-lookup"><span data-stu-id="c053f-114">Remarks</span></span>

<span data-ttu-id="c053f-115">在首次提交邮件时, 客户端应用程序应将此属性设置为与**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 属性相同的值。</span><span class="sxs-lookup"><span data-stu-id="c053f-115">A client application should set this property to the same value as the **PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) property when the message is first submitted.</span></span> <span data-ttu-id="c053f-116">不应随后再更改它。</span><span class="sxs-lookup"><span data-stu-id="c053f-116">It should never be changed subsequently.</span></span>
  
<span data-ttu-id="c053f-117">传输提供程序使用此属性来保护已复制的项的灵敏度。</span><span class="sxs-lookup"><span data-stu-id="c053f-117">This property is used by the transport provider to protect the sensitivity on copied entries.</span></span> <span data-ttu-id="c053f-118">例如, 它使其能够在转发或回复最初标记为 " **SENSITIVITY_PRIVATE**" 的邮件中阻止对原始邮件文本的修改。</span><span class="sxs-lookup"><span data-stu-id="c053f-118">It enables it, for example, to block modification of the original message text in a forward of or reply to a message that was originally marked **SENSITIVITY_PRIVATE**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="c053f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="c053f-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c053f-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="c053f-120">Protocol specifications</span></span>

<span data-ttu-id="c053f-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c053f-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c053f-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="c053f-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="c053f-123">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c053f-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c053f-124">指定在电子邮件对象上允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="c053f-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c053f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="c053f-125">Header files</span></span>

<span data-ttu-id="c053f-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c053f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="c053f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c053f-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="c053f-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="c053f-128">Mapitags.h</span></span>
  
> <span data-ttu-id="c053f-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c053f-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c053f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c053f-130">See also</span></span>



[<span data-ttu-id="c053f-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c053f-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c053f-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c053f-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c053f-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c053f-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c053f-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c053f-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

