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
ms.openlocfilehash: 45d4b0bfe7f902ee2cfe1d735c990d80f8fbb60d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588942"
---
# <a name="pidtagattachrendering-canonical-property"></a><span data-ttu-id="0be1e-103">PidTagAttachRendering 规范属性</span><span class="sxs-lookup"><span data-stu-id="0be1e-103">PidTagAttachRendering Canonical Property</span></span>

  
  
<span data-ttu-id="0be1e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0be1e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0be1e-105">包含附件的呈现信息与 Microsoft Windows 图元文件。</span><span class="sxs-lookup"><span data-stu-id="0be1e-105">Contains a Microsoft Windows metafile with rendering information for an attachment.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0be1e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0be1e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0be1e-107">PR_ATTACH_RENDERING</span><span class="sxs-lookup"><span data-stu-id="0be1e-107">PR_ATTACH_RENDERING</span></span>  <br/> |
|<span data-ttu-id="0be1e-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0be1e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0be1e-109">0x3709</span><span class="sxs-lookup"><span data-stu-id="0be1e-109">0x3709</span></span>  <br/> |
|<span data-ttu-id="0be1e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0be1e-110">Data type:</span></span>  <br/> |<span data-ttu-id="0be1e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0be1e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0be1e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0be1e-112">Area:</span></span>  <br/> |<span data-ttu-id="0be1e-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="0be1e-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0be1e-114">注解</span><span class="sxs-lookup"><span data-stu-id="0be1e-114">Remarks</span></span>

<span data-ttu-id="0be1e-115">此属性的用途是提供的图标或其他可在附件点父消息中显示的图形表示。</span><span class="sxs-lookup"><span data-stu-id="0be1e-115">The purpose of this property is to provide an icon or other pictorial representation that can be displayed within the parent message at the point of attachment.</span></span> <span data-ttu-id="0be1e-116">此类表示通常包括附件，如果有的名称和附件，如 Microsoft Office Word 文档的特性。</span><span class="sxs-lookup"><span data-stu-id="0be1e-116">Such representation typically includes the name of the attachment, if any, and the nature of the attachment, such as a Microsoft Office Word document.</span></span> <span data-ttu-id="0be1e-117">客户端应用程序可以在显示的邮件使用这种表示形式。</span><span class="sxs-lookup"><span data-stu-id="0be1e-117">A client application can use this representation in the display of the message.</span></span> 
  
<span data-ttu-id="0be1e-118">附加文件，此属性通常描绘文件图标。</span><span class="sxs-lookup"><span data-stu-id="0be1e-118">For an attached file, this property usually portrays an icon for the file.</span></span> 
  
<span data-ttu-id="0be1e-119">对于附加消息，通常不设置此属性。</span><span class="sxs-lookup"><span data-stu-id="0be1e-119">For an attached message, this property is typically not set.</span></span> <span data-ttu-id="0be1e-120">无需呈现附加的邮件客户端应用程序应获取其**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性，请指向相应的窗体信息对象的指针调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)打开[IMAPIFormInfo](imapiforminfoimapiprop.md)界面在该对象，并使用**GetProps**检索**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0be1e-120">A client application needing to render an attached message should obtain its **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) property, call [IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md) for a pointer to the corresponding form information object, open the [IMAPIFormInfo](imapiforminfoimapiprop.md) interface on that object, and use **GetProps** to retrieve the **PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) or **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="0be1e-121">静态 OLE 嵌入对象，此属性包含可用于在窗口中绘制的附件表示 Microsoft Windows 图元文件。</span><span class="sxs-lookup"><span data-stu-id="0be1e-121">For an embedded static OLE object, this property contains a Microsoft Windows metafile that can be used to draw the attachment representation in a window.</span></span> 
  
<span data-ttu-id="0be1e-122">对于嵌入动态 OLE 对象，客户应使用 OLE 数据生成呈现信息。</span><span class="sxs-lookup"><span data-stu-id="0be1e-122">For an embedded dynamic OLE object, the client should use the OLE data to generate the rendering information.</span></span> 
  
<span data-ttu-id="0be1e-123">在所有情况下，客户端应用程序应请注意，此属性通常是大小为多个几百个字节，受制截断附件表中。</span><span class="sxs-lookup"><span data-stu-id="0be1e-123">In all cases, the client application should be aware that this property is usually several hundred bytes in size and is subject to truncation in the attachment table.</span></span> <span data-ttu-id="0be1e-124">如果希望此属性中的附件呈现而无需打开附件本身客户端，它必须工作表截断规则内。</span><span class="sxs-lookup"><span data-stu-id="0be1e-124">If a client wishes to render the attachment from this property without opening the attachment itself, it must work within the table truncation rule.</span></span> <span data-ttu-id="0be1e-125">有关详细信息，请参阅[处理大型列](working-with-large-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="0be1e-125">For more information, see [Working with Large Columns](working-with-large-columns.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0be1e-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="0be1e-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0be1e-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="0be1e-127">Protocol specifications</span></span>

<span data-ttu-id="0be1e-128">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0be1e-128">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0be1e-129">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="0be1e-129">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0be1e-130">头文件</span><span class="sxs-lookup"><span data-stu-id="0be1e-130">Header files</span></span>

<span data-ttu-id="0be1e-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0be1e-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="0be1e-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0be1e-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="0be1e-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0be1e-133">Mapitags.h</span></span>
  
> <span data-ttu-id="0be1e-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0be1e-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0be1e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0be1e-135">See also</span></span>



[<span data-ttu-id="0be1e-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0be1e-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0be1e-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0be1e-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0be1e-138">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0be1e-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0be1e-139">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0be1e-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

