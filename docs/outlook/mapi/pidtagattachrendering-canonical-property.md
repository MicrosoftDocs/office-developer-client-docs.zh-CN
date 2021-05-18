---
title: PidTagAttachRendering 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachRendering
api_type:
- HeaderDef
ms.assetid: 1f31f7f4-fbda-4337-95e5-5474dd1bf84a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 22d3e649641dbe688912ecece7fde73a555f4a88
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361094"
---
# <a name="pidtagattachrendering-canonical-property"></a><span data-ttu-id="a4533-103">PidTagAttachRendering 规范属性</span><span class="sxs-lookup"><span data-stu-id="a4533-103">PidTagAttachRendering Canonical Property</span></span>

  
  
<span data-ttu-id="a4533-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4533-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4533-105">包含一个 Microsoft Windows图元文件，其中包含附件的呈现信息。</span><span class="sxs-lookup"><span data-stu-id="a4533-105">Contains a Microsoft Windows metafile with rendering information for an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4533-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a4533-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a4533-107">PR_ATTACH_RENDERING</span><span class="sxs-lookup"><span data-stu-id="a4533-107">PR_ATTACH_RENDERING</span></span>  <br/> |
|<span data-ttu-id="a4533-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a4533-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a4533-109">0x3709</span><span class="sxs-lookup"><span data-stu-id="a4533-109">0x3709</span></span>  <br/> |
|<span data-ttu-id="a4533-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a4533-110">Data type:</span></span>  <br/> |<span data-ttu-id="a4533-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="a4533-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="a4533-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a4533-112">Area:</span></span>  <br/> |<span data-ttu-id="a4533-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="a4533-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a4533-114">备注</span><span class="sxs-lookup"><span data-stu-id="a4533-114">Remarks</span></span>

<span data-ttu-id="a4533-115">此属性的目的是提供图标或其他十二点活字表示形式，可以在父邮件中的附件点显示。</span><span class="sxs-lookup"><span data-stu-id="a4533-115">The purpose of this property is to provide an icon or other pictorial representation that can be displayed within the parent message at the point of attachment.</span></span> <span data-ttu-id="a4533-116">此类表示形式通常包括附件的名称（如果有）和附件的性质，如Microsoft Office Word 文档。</span><span class="sxs-lookup"><span data-stu-id="a4533-116">Such representation typically includes the name of the attachment, if any, and the nature of the attachment, such as a Microsoft Office Word document.</span></span> <span data-ttu-id="a4533-117">客户端应用程序可以在消息的显示中使用此表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4533-117">A client application can use this representation in the display of the message.</span></span> 
  
<span data-ttu-id="a4533-118">对于附加的文件，此属性通常会显示该文件的图标。</span><span class="sxs-lookup"><span data-stu-id="a4533-118">For an attached file, this property usually portrays an icon for the file.</span></span> 
  
<span data-ttu-id="a4533-119">对于附加的邮件，通常不设置此属性。</span><span class="sxs-lookup"><span data-stu-id="a4533-119">For an attached message, this property is typically not set.</span></span> <span data-ttu-id="a4533-120">需要呈现附加邮件的客户端应用程序应PR_MESSAGE_CLASS ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性， 调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md)获取指向相应表单信息对象的指针，打开该对象上的 [IMAPIFormInfo](imapiforminfoimapiprop.md)接口，并使用 **GetProps** 检索 **PR_ICON** ( [PidTagIcon](pidtagicon-canonical-property.md)) 或 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="a4533-120">A client application needing to render an attached message should obtain its **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property, call [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) for a pointer to the corresponding form information object, open the [IMAPIFormInfo](imapiforminfoimapiprop.md) interface on that object, and use **GetProps** to retrieve the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="a4533-121">对于嵌入的静态 OLE 对象，此属性包含一个 Microsoft Windows图元文件，该图元文件可用于在窗口中绘制附件表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4533-121">For an embedded static OLE object, this property contains a Microsoft Windows metafile that can be used to draw the attachment representation in a window.</span></span> 
  
<span data-ttu-id="a4533-122">对于嵌入的动态 OLE 对象，客户端应该使用 OLE 数据生成呈现信息。</span><span class="sxs-lookup"><span data-stu-id="a4533-122">For an embedded dynamic OLE object, the client should use the OLE data to generate the rendering information.</span></span> 
  
<span data-ttu-id="a4533-123">在所有这些情况下，客户端应用程序都应了解此属性的大小通常为几百字节，并可能会截断附件表中的数据。</span><span class="sxs-lookup"><span data-stu-id="a4533-123">In all cases, the client application should be aware that this property is usually several hundred bytes in size and is subject to truncation in the attachment table.</span></span> <span data-ttu-id="a4533-124">如果客户端希望从此属性呈现附件而不打开附件本身，则必须在表截断规则中工作。</span><span class="sxs-lookup"><span data-stu-id="a4533-124">If a client wishes to render the attachment from this property without opening the attachment itself, it must work within the table truncation rule.</span></span> <span data-ttu-id="a4533-125">有关详细信息，请参阅 [使用大列](working-with-large-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="a4533-125">For more information, see [Working with Large Columns](working-with-large-columns.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a4533-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="a4533-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a4533-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="a4533-127">Protocol specifications</span></span>

<span data-ttu-id="a4533-128">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4533-128">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a4533-129">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a4533-129">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a4533-130">头文件</span><span class="sxs-lookup"><span data-stu-id="a4533-130">Header files</span></span>

<span data-ttu-id="a4533-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a4533-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="a4533-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a4533-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="a4533-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a4533-133">Mapitags.h</span></span>
  
> <span data-ttu-id="a4533-134">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a4533-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a4533-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4533-135">See also</span></span>



[<span data-ttu-id="a4533-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a4533-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a4533-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a4533-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a4533-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a4533-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a4533-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a4533-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

