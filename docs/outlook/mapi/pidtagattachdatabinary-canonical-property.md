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
ms.openlocfilehash: 1a5f8688b8ea747590cf2a2d6d5efb271aa488f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356544"
---
# <a name="pidtagattachdatabinary-canonical-property"></a><span data-ttu-id="d8366-103">PidTagAttachDataBinary 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8366-103">PidTagAttachDataBinary Canonical Property</span></span>

  
  
<span data-ttu-id="d8366-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d8366-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d8366-105">包含通常通过对象链接和嵌入 **IStream** 接口 (OLE) 二进制附件数据。</span><span class="sxs-lookup"><span data-stu-id="d8366-105">Contains binary attachment data typically accessed through the Object Linking and Embedding (OLE) **IStream** interface.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d8366-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d8366-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d8366-107">PR_ATTACH_DATA_BIN</span><span class="sxs-lookup"><span data-stu-id="d8366-107">PR_ATTACH_DATA_BIN</span></span>  <br/> |
|<span data-ttu-id="d8366-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d8366-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d8366-109">0x3701</span><span class="sxs-lookup"><span data-stu-id="d8366-109">0x3701</span></span>  <br/> |
|<span data-ttu-id="d8366-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d8366-110">Data type:</span></span>  <br/> |<span data-ttu-id="d8366-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d8366-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d8366-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d8366-112">Area:</span></span>  <br/> |<span data-ttu-id="d8366-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="d8366-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d8366-114">备注</span><span class="sxs-lookup"><span data-stu-id="d8366-114">Remarks</span></span>

<span data-ttu-id="d8366-115">当 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值为 ATTACH_BY_VALUE 时，此属性保留附件，这是常用的 attachment 方法，也是唯一需要支持的方法。</span><span class="sxs-lookup"><span data-stu-id="d8366-115">This property holds the attachment when the value of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property is ATTACH_BY_VALUE, which is the usual attachment method and the only one required to be supported.</span></span> <span data-ttu-id="d8366-116">**PR_ATTACH_DATA_BIN** OLE 1.0 OLESTREAM 附件时，PR_ATTACH_METHOD **OLESTREAM** **ATTACH_OLE。**</span><span class="sxs-lookup"><span data-stu-id="d8366-116">**PR_ATTACH_DATA_BIN** also holds an OLE 1.0 **OLESTREAM** attachment when the value of **PR_ATTACH_METHOD** is ATTACH_OLE.</span></span> 
  
 <span data-ttu-id="d8366-117">**OLESTREAM** 附件可以通过调用 OLE **IStream：：CopyTo** 方法复制到文件中。</span><span class="sxs-lookup"><span data-stu-id="d8366-117">**OLESTREAM** attachments can be copied into a file by calling the OLE **IStream::CopyTo** method.</span></span> <span data-ttu-id="d8366-118">OLE 编码类型可以从[PidTagAttachTag PR_ATTACH_TAG (PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定。 </span><span class="sxs-lookup"><span data-stu-id="d8366-118">The OLE encoding type can be determined from the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="d8366-119">对于 OLE 文档文件附件，邮件存储提供程序必须对 PR_ATTACH_DATA_OBJ ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md) **)** 上的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)调用做出响应，并且可以选择响应 **对 PR_ATTACH_DATA_BIN 的调用**。</span><span class="sxs-lookup"><span data-stu-id="d8366-119">For an OLE document file attachment, the message store provider must respond to an [IMAPIProp::OpenProperty](imapiprop-openproperty.md) call on **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) and may optionally respond to a call on **PR_ATTACH_DATA_BIN**.</span></span> <span data-ttu-id="d8366-120">请注意 **，PR_ATTACH_DATA_BIN** 和 **PR_ATTACH_DATA_OBJ** 共享同一属性标识符，因此是同一属性的两个表示形式。</span><span class="sxs-lookup"><span data-stu-id="d8366-120">Note that **PR_ATTACH_DATA_BIN** and **PR_ATTACH_DATA_OBJ** share the same property identifier and thus are two renditions of the same property.</span></span> 
  
<span data-ttu-id="d8366-121">对于存储对象（如 OLE 2.0 docfile 格式的复合文件）来说，某些服务提供程序允许使用 MAPI **IStreamDocfile** 接口打开该对象，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="d8366-121">For a storage object, such as a compound file in OLE 2.0 docfile format, some service providers allow it to be opened with the MAPI **IStreamDocfile** interface for improved performance.</span></span> <span data-ttu-id="d8366-122">支持 **IStreamDocfile** 的提供程序必须在 PR_ATTACH_DATA_OBJ 上公开它 **，** 并且可以选择在 PR_ATTACH_DATA_BIN 上 **公开** 它。</span><span class="sxs-lookup"><span data-stu-id="d8366-122">A provider that supports **IStreamDocfile** must expose it on **PR_ATTACH_DATA_OBJ** and may optionally expose it on **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="d8366-123">有关 OLE 接口和格式的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d8366-123">For more information on OLE interfaces and formats, see [OLE and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d8366-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="d8366-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d8366-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="d8366-125">Protocol specifications</span></span>

<span data-ttu-id="d8366-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d8366-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d8366-127">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d8366-127">Handles message and attachment objects.</span></span>
    
## <a name="header-files"></a><span data-ttu-id="d8366-128">头文件</span><span class="sxs-lookup"><span data-stu-id="d8366-128">Header Files</span></span>

<span data-ttu-id="d8366-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d8366-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="d8366-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d8366-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="d8366-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d8366-131">Mapitags.h</span></span>
  
> <span data-ttu-id="d8366-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d8366-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d8366-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8366-133">See also</span></span>



[<span data-ttu-id="d8366-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d8366-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d8366-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d8366-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d8366-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d8366-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d8366-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d8366-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

