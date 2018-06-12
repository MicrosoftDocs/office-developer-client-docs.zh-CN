---
title: PidTagAttachDataObject 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachDataObject
api_type:
- HeaderDef
ms.assetid: b76312c6-7682-4ded-be25-55e21b0b091b
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b3fc7690a8c9eb2ada3a34bc44217ff463721e4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777327"
---
# <a name="pidtagattachdataobject-canonical-property"></a><span data-ttu-id="bb694-103">PidTagAttachDataObject 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb694-103">PidTagAttachDataObject Canonical Property</span></span>

  
  
<span data-ttu-id="bb694-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bb694-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bb694-105">包含通常通过对象链接和嵌入 (OLE) **IStorage**界面访问一个 attachment 对象。</span><span class="sxs-lookup"><span data-stu-id="bb694-105">Contains an attachment object typically accessed through the Object Linking and Embedding (OLE) **IStorage** interface.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb694-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="bb694-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bb694-107">PR_ATTACH_DATA_OBJ</span><span class="sxs-lookup"><span data-stu-id="bb694-107">PR_ATTACH_DATA_OBJ</span></span>  <br/> |
|<span data-ttu-id="bb694-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="bb694-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bb694-109">0x3701</span><span class="sxs-lookup"><span data-stu-id="bb694-109">0x3701</span></span>  <br/> |
|<span data-ttu-id="bb694-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bb694-110">Data type:</span></span>  <br/> |<span data-ttu-id="bb694-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="bb694-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="bb694-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bb694-112">Area:</span></span>  <br/> |<span data-ttu-id="bb694-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="bb694-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb694-114">备注</span><span class="sxs-lookup"><span data-stu-id="bb694-114">Remarks</span></span>

<span data-ttu-id="bb694-115">**ATTACH_EMBEDDED_MSG**或**ATTACH_OLE** **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值时，此属性包含附件。</span><span class="sxs-lookup"><span data-stu-id="bb694-115">This property holds the attachment when the value of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property is **ATTACH_EMBEDDED_MSG** or **ATTACH_OLE**.</span></span> <span data-ttu-id="bb694-116">可从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定 OLE 编码类型。</span><span class="sxs-lookup"><span data-stu-id="bb694-116">The OLE encoding type can be determined from **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)).</span></span> 
  
<span data-ttu-id="bb694-117">与**ATTACH_EMBEDDED_MSG**值相关联的附件， [IMessage:IMAPIProp](imessageimapiprop.md)接口可用于更快地访问。</span><span class="sxs-lookup"><span data-stu-id="bb694-117">For an attachment associated with the **ATTACH_EMBEDDED_MSG** value, the [IMessage:IMAPIProp](imessageimapiprop.md) interface can be used for faster access.</span></span> 
  
<span data-ttu-id="bb694-118">动态 OLE 嵌入对象， **PR_ATTACH_DATA_OBJ**属性包含自己呈现的信息，并**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 属性应为空或不存在。</span><span class="sxs-lookup"><span data-stu-id="bb694-118">For an embedded dynamic OLE object, the **PR_ATTACH_DATA_OBJ** property contains its own rendering information, and the **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) property should be either nonexistent or empty.</span></span> 
  
<span data-ttu-id="bb694-119">OLE 文档文件附件，消息存储提供程序必须响应上**PR_ATTACH_DATA_OBJ** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)呼叫，并 （可选） 可能响应**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)上的呼叫).</span><span class="sxs-lookup"><span data-stu-id="bb694-119">For an OLE document file attachment, the message store provider must respond to an [IMAPIProp::OpenProperty](imapiprop-openproperty.md) call on **PR_ATTACH_DATA_OBJ** and may optionally respond to a call on **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)).</span></span> <span data-ttu-id="bb694-120">**PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**属性共享相同属性标识符，因此都是相同的属性的两个呈现形式。</span><span class="sxs-lookup"><span data-stu-id="bb694-120">The **PR_ATTACH_DATA_BIN** and **PR_ATTACH_DATA_OBJ** properties share the same property identifier and thus are two renditions of the same property.</span></span> 
  
<span data-ttu-id="bb694-121">对于存储对象，例如复合文件格式 docfile OLE 2.0，某些服务提供商允许其使用 MAPI **IStreamDocfile**界面，不包含任何其他成员，旨在优化性能的**IStream**子类打开。</span><span class="sxs-lookup"><span data-stu-id="bb694-121">For a storage object, such as a compound file in OLE 2.0 docfile format, some service providers allow it to be opened with the MAPI **IStreamDocfile** interface, a subclass of **IStream** with no additional members, designed to optimize performance.</span></span> <span data-ttu-id="bb694-122">潜在保存已足够 justify 尝试打开**PR_ATTACH_DATA_OBJ**通过**IStreamDocfile**。</span><span class="sxs-lookup"><span data-stu-id="bb694-122">The potential saving is enough to justify attempting to open **PR_ATTACH_DATA_OBJ** through **IStreamDocfile**.</span></span> <span data-ttu-id="bb694-123">如果返回**MAPI_E_INTERFACE_NOT_SUPPORTED** ，客户端就可以与**IStream**中打开**PR_ATTACH_DATA_BIN** 。</span><span class="sxs-lookup"><span data-stu-id="bb694-123">If **MAPI_E_INTERFACE_NOT_SUPPORTED** is returned, the client can then open **PR_ATTACH_DATA_BIN** with **IStream**.</span></span> 
  
<span data-ttu-id="bb694-124">如果客户端应用程序或服务提供商不能使用**PR_ATTACH_METHOD**借助**PR_ATTACH_DATA_OBJ**打开附件子对象，它应使用**PR_ATTACH_DATA_BIN**。</span><span class="sxs-lookup"><span data-stu-id="bb694-124">If the client application or service provider cannot open an attachment subobject by using **PR_ATTACH_DATA_OBJ** with the help of **PR_ATTACH_METHOD**, it should use **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="bb694-125">OLE 接口和格式的详细信息，请参阅[OLE 和数据传输](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bb694-125">For more information on OLE interfaces and formats, see [OLE and Data Transfer](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="bb694-126">相关资源</span><span class="sxs-lookup"><span data-stu-id="bb694-126">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bb694-127">协议规范</span><span class="sxs-lookup"><span data-stu-id="bb694-127">Protocol specifications</span></span>

<span data-ttu-id="bb694-128">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb694-128">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bb694-129">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="bb694-129">Handles message and attachment objects.</span></span>
    
## <a name="header-files"></a><span data-ttu-id="bb694-130">头文件</span><span class="sxs-lookup"><span data-stu-id="bb694-130">Header Files</span></span>

<span data-ttu-id="bb694-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb694-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="bb694-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bb694-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="bb694-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bb694-133">Mapitags.h</span></span>
  
> <span data-ttu-id="bb694-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bb694-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bb694-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb694-135">See also</span></span>



[<span data-ttu-id="bb694-136">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bb694-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bb694-137">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bb694-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bb694-138">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb694-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bb694-139">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bb694-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

