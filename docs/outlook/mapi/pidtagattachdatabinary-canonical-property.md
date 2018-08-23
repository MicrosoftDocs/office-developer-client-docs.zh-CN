---
title: PidTagAttachDataBinary 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachDataBinary
api_type:
- HeaderDef
ms.assetid: 3b0a8b28-863e-4b96-a4c0-fdb8f40555b9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 629746cedf8c6f4a8c960912a9ab1bcdc7a09e9e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574144"
---
# <a name="pidtagattachdatabinary-canonical-property"></a><span data-ttu-id="8d5c7-103">PidTagAttachDataBinary 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d5c7-103">PidTagAttachDataBinary Canonical Property</span></span>

  
  
<span data-ttu-id="8d5c7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8d5c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8d5c7-105">包含通常通过对象链接和嵌入 (OLE) **IStream**接口访问的二进制附件数据。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-105">Contains binary attachment data typically accessed through the Object Linking and Embedding (OLE) **IStream** interface.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8d5c7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8d5c7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8d5c7-107">PR_ATTACH_DATA_BIN</span><span class="sxs-lookup"><span data-stu-id="8d5c7-107">PR_ATTACH_DATA_BIN</span></span>  <br/> |
|<span data-ttu-id="8d5c7-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8d5c7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8d5c7-109">0x3701</span><span class="sxs-lookup"><span data-stu-id="8d5c7-109">0x3701</span></span>  <br/> |
|<span data-ttu-id="8d5c7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8d5c7-110">Data type:</span></span>  <br/> |<span data-ttu-id="8d5c7-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="8d5c7-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="8d5c7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8d5c7-112">Area:</span></span>  <br/> |<span data-ttu-id="8d5c7-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="8d5c7-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8d5c7-114">注解</span><span class="sxs-lookup"><span data-stu-id="8d5c7-114">Remarks</span></span>

<span data-ttu-id="8d5c7-115">此属性包含附件时**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值是 ATTACH_BY_VALUE，这是您的常用附件方法和必须支持的唯一一个。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-115">This property holds the attachment when the value of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property is ATTACH_BY_VALUE, which is the usual attachment method and the only one required to be supported.</span></span> <span data-ttu-id="8d5c7-116">**PR_ATTACH_DATA_BIN** ATTACH_OLE **PR_ATTACH_METHOD**的值时，还包含 OLE 1.0 **OLESTREAM**附件。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-116">**PR_ATTACH_DATA_BIN** also holds an OLE 1.0 **OLESTREAM** attachment when the value of **PR_ATTACH_METHOD** is ATTACH_OLE.</span></span> 
  
 <span data-ttu-id="8d5c7-117">**OLESTREAM**附件可以复制到文件中，通过调用 OLE **IStream::CopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-117">**OLESTREAM** attachments can be copied into a file by calling the OLE **IStream::CopyTo** method.</span></span> <span data-ttu-id="8d5c7-118">可以从**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 属性确定 OLE 编码类型。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-118">The OLE encoding type can be determined from the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="8d5c7-119">OLE 文档文件附件，消息存储提供程序必须响应[IMAPIProp::OpenProperty](imapiprop-openproperty.md)呼叫的**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))，并 （可选） 可能响应**PR_ATTACH_DATA_BIN 上的呼叫**.</span><span class="sxs-lookup"><span data-stu-id="8d5c7-119">For an OLE document file attachment, the message store provider must respond to an [IMAPIProp::OpenProperty](imapiprop-openproperty.md) call on **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) and may optionally respond to a call on **PR_ATTACH_DATA_BIN**.</span></span> <span data-ttu-id="8d5c7-120">请注意， **PR_ATTACH_DATA_BIN**和**PR_ATTACH_DATA_OBJ**共享相同属性标识符，因此都是相同的属性的两个呈现形式。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-120">Note that **PR_ATTACH_DATA_BIN** and **PR_ATTACH_DATA_OBJ** share the same property identifier and thus are two renditions of the same property.</span></span> 
  
<span data-ttu-id="8d5c7-121">对于存储对象，例如复合文件格式 docfile OLE 2.0，某些服务提供商允许其打开与 MAPI **IStreamDocfile**接口以提高性能。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-121">For a storage object, such as a compound file in OLE 2.0 docfile format, some service providers allow it to be opened with the MAPI **IStreamDocfile** interface for improved performance.</span></span> <span data-ttu-id="8d5c7-122">支持**IStreamDocfile**的提供程序必须公开其**PR_ATTACH_DATA_OBJ**上，并可能 （可选） 将其公开**PR_ATTACH_DATA_BIN**上。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-122">A provider that supports **IStreamDocfile** must expose it on **PR_ATTACH_DATA_OBJ** and may optionally expose it on **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="8d5c7-123">OLE 接口和格式的详细信息，请参阅[OLE 和数据传输](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-123">For more information on OLE interfaces and formats, see [OLE and Data Transfer](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8d5c7-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="8d5c7-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8d5c7-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="8d5c7-125">Protocol specifications</span></span>

<span data-ttu-id="8d5c7-126">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8d5c7-126">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8d5c7-127">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-127">Handles message and attachment objects.</span></span>
    
## <a name="header-files"></a><span data-ttu-id="8d5c7-128">头文件</span><span class="sxs-lookup"><span data-stu-id="8d5c7-128">Header Files</span></span>

<span data-ttu-id="8d5c7-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8d5c7-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="8d5c7-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="8d5c7-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8d5c7-131">Mapitags.h</span></span>
  
> <span data-ttu-id="8d5c7-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8d5c7-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8d5c7-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d5c7-133">See also</span></span>



[<span data-ttu-id="8d5c7-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8d5c7-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8d5c7-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8d5c7-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8d5c7-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8d5c7-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8d5c7-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8d5c7-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

