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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6d461c88e96a3f749595b3e071737107480472aa
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777968"
---
# <a name="pidtagoriginalsensitivity-canonical-property"></a><span data-ttu-id="3cea9-103">PidTagOriginalSensitivity 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cea9-103">PidTagOriginalSensitivity Canonical Property</span></span>

  
  
<span data-ttu-id="3cea9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3cea9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cea9-105">包含分配发件人的邮件的第一个版本的敏感度值，即之前正在转发或答复邮件。</span><span class="sxs-lookup"><span data-stu-id="3cea9-105">Contains the sensitivity value assigned by the sender of the first version of a message that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cea9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="3cea9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3cea9-107">PR_ORIGINAL_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="3cea9-107">PR_ORIGINAL_SENSITIVITY</span></span>  <br/> |
|<span data-ttu-id="3cea9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3cea9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3cea9-109">0x002E</span><span class="sxs-lookup"><span data-stu-id="3cea9-109">0x002E</span></span>  <br/> |
|<span data-ttu-id="3cea9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3cea9-110">Data type:</span></span>  <br/> |<span data-ttu-id="3cea9-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="3cea9-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="3cea9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3cea9-112">Area:</span></span>  <br/> |<span data-ttu-id="3cea9-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="3cea9-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cea9-114">备注</span><span class="sxs-lookup"><span data-stu-id="3cea9-114">Remarks</span></span>

<span data-ttu-id="3cea9-115">为第一个邮件时的**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) 属性已提交，客户端应用程序应为相同的值设置该属性。</span><span class="sxs-lookup"><span data-stu-id="3cea9-115">A client application should set this property to the same value as the **PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md)) property when the message is first submitted.</span></span> <span data-ttu-id="3cea9-116">它应永远不会更改随后。</span><span class="sxs-lookup"><span data-stu-id="3cea9-116">It should never be changed subsequently.</span></span>
  
<span data-ttu-id="3cea9-117">此属性由传输提供程序用于保护上复制的条目的敏感度。</span><span class="sxs-lookup"><span data-stu-id="3cea9-117">This property is used by the transport provider to protect the sensitivity on copied entries.</span></span> <span data-ttu-id="3cea9-118">使它，例如，若要阻止原始消息文本的转发或答复最初被标记**SENSITIVITY_PRIVATE**一条消息中的修改。</span><span class="sxs-lookup"><span data-stu-id="3cea9-118">It enables it, for example, to block modification of the original message text in a forward of or reply to a message that was originally marked **SENSITIVITY_PRIVATE**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3cea9-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3cea9-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3cea9-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="3cea9-120">Protocol specifications</span></span>

<span data-ttu-id="3cea9-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cea9-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cea9-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="3cea9-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="3cea9-123">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3cea9-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3cea9-124">指定的属性和电子邮件消息对象在允许的操作。</span><span class="sxs-lookup"><span data-stu-id="3cea9-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3cea9-125">头文件</span><span class="sxs-lookup"><span data-stu-id="3cea9-125">Header files</span></span>

<span data-ttu-id="3cea9-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3cea9-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="3cea9-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3cea9-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="3cea9-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3cea9-128">Mapitags.h</span></span>
  
> <span data-ttu-id="3cea9-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3cea9-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3cea9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cea9-130">See also</span></span>



[<span data-ttu-id="3cea9-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3cea9-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3cea9-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3cea9-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3cea9-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cea9-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3cea9-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3cea9-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

