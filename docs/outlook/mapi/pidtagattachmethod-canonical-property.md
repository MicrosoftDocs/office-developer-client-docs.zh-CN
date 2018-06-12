---
title: PidTagAttachMethod 规范属性
manager: soliver
ms.date: 9/7/2016
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachMethod
api_type:
- HeaderDef
ms.assetid: 32089213-ef7b-4152-84ab-b44e9911332b
description: 上次修改时间： 9 月 7，2016年
ms.openlocfilehash: 1720e9a2eeb54daed1e559f99b0c63ce09585419
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777365"
---
# <a name="pidtagattachmethod-canonical-property"></a><span data-ttu-id="592d7-103">PidTagAttachMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="592d7-103">PidTagAttachMethod Canonical Property</span></span>

 
  
<span data-ttu-id="592d7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="592d7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="592d7-105">包含一个 MAPI 定义的常数，表示可以访问附件的内容的方式。</span><span class="sxs-lookup"><span data-stu-id="592d7-105">Contains a MAPI-defined constant representing the way the contents of an attachment can be accessed.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="592d7-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="592d7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="592d7-107">PR_ATTACH_METHOD</span><span class="sxs-lookup"><span data-stu-id="592d7-107">PR_ATTACH_METHOD</span></span>  <br/> |
|<span data-ttu-id="592d7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="592d7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="592d7-109">0x3705</span><span class="sxs-lookup"><span data-stu-id="592d7-109">0x3705</span></span>  <br/> |
|<span data-ttu-id="592d7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="592d7-110">Data type:</span></span>  <br/> |<span data-ttu-id="592d7-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="592d7-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="592d7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="592d7-112">Area:</span></span>  <br/> |<span data-ttu-id="592d7-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="592d7-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="592d7-114">备注</span><span class="sxs-lookup"><span data-stu-id="592d7-114">Remarks</span></span>

<span data-ttu-id="592d7-115">此属性可以具有完全下列值之一：</span><span class="sxs-lookup"><span data-stu-id="592d7-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="592d7-116">NO_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="592d7-116">NO_ATTACHMENT</span></span> 
  
> <span data-ttu-id="592d7-117">刚刚创建的附件。</span><span class="sxs-lookup"><span data-stu-id="592d7-117">The attachment has just been created.</span></span> 
    
<span data-ttu-id="592d7-118">ATTACH_BY_VALUE</span><span class="sxs-lookup"><span data-stu-id="592d7-118">ATTACH_BY_VALUE</span></span> 
  
> <span data-ttu-id="592d7-119">**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性包含附件数据。</span><span class="sxs-lookup"><span data-stu-id="592d7-119">The **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property contains the attachment data.</span></span> 
    
<span data-ttu-id="592d7-120">ATTACH_BY_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="592d7-120">ATTACH_BY_REFERENCE</span></span> 
  
> <span data-ttu-id="592d7-121">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含标识有权访问公共文件附件形式向收件人的完全限定路径服务器。</span><span class="sxs-lookup"><span data-stu-id="592d7-121">The **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) or **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) property contains a fully-qualified path identifying the attachment to recipients with access to a common file server.</span></span> 
    
<span data-ttu-id="592d7-122">ATTACH_BY_REF_RESOLVE</span><span class="sxs-lookup"><span data-stu-id="592d7-122">ATTACH_BY_REF_RESOLVE</span></span> 
  
> <span data-ttu-id="592d7-123">**PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="592d7-123">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="592d7-124">ATTACH_BY_REF_ONLY</span><span class="sxs-lookup"><span data-stu-id="592d7-124">ATTACH_BY_REF_ONLY</span></span> 
  
> <span data-ttu-id="592d7-125">**PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="592d7-125">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="592d7-126">ATTACH_EMBEDDED_MSG</span><span class="sxs-lookup"><span data-stu-id="592d7-126">ATTACH_EMBEDDED_MSG</span></span> 
  
> <span data-ttu-id="592d7-127">**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性包含支持**IMessage**接口的嵌入的对象。</span><span class="sxs-lookup"><span data-stu-id="592d7-127">The **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property contains an embedded object that supports the **IMessage** interface.</span></span> 
    
<span data-ttu-id="592d7-128">ATTACH_OLE</span><span class="sxs-lookup"><span data-stu-id="592d7-128">ATTACH_OLE</span></span> 
  
> <span data-ttu-id="592d7-129">附件是嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="592d7-129">The attachment is an embedded OLE object.</span></span>
    
<span data-ttu-id="592d7-130">ATTACH_BY_WEBREFERENCE</span><span class="sxs-lookup"><span data-stu-id="592d7-130">ATTACH_BY_WEBREFERENCE</span></span> 
  
> <span data-ttu-id="592d7-131">附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="592d7-131">The attachment content is not in the message.</span></span> 
    
<span data-ttu-id="592d7-132">在创建时，所有的 attachment 对象具有**NO_ATTACHMENT** **PR_ATTACH_METHOD**初始值。</span><span class="sxs-lookup"><span data-stu-id="592d7-132">When created, all attachment objects have an initial **PR_ATTACH_METHOD** value of **NO_ATTACHMENT**.</span></span> 
  
<span data-ttu-id="592d7-133">客户端应用程序和服务提供程序只需支持**ATTACH_BY_VALUE**值表示的附件方法。</span><span class="sxs-lookup"><span data-stu-id="592d7-133">Client applications and service providers are only required to support the attachment method represented by the **ATTACH_BY_VALUE** value.</span></span> <span data-ttu-id="592d7-134">其他附件方法是可选的。</span><span class="sxs-lookup"><span data-stu-id="592d7-134">The other attachment methods are optional.</span></span> <span data-ttu-id="592d7-135">消息存储不强制实施的**PR_ATTACH_METHOD**值和其他附件属性的值之间的任何一致性。</span><span class="sxs-lookup"><span data-stu-id="592d7-135">The message store does not enforce any consistency between the value of **PR_ATTACH_METHOD** and the values of the other attachment properties.</span></span> 
  
<span data-ttu-id="592d7-136">对于完全限定路径，应使用**ATTACH_BY_REF_ONLY** **ATTACH_BY_REFERENCE**与建议都使用通用命名约定 (UNC) 名称。</span><span class="sxs-lookup"><span data-stu-id="592d7-136">Universal naming convention (UNC) names are recommended for fully-qualified paths, which should be used with **ATTACH_BY_REFERENCE** and **ATTACH_BY_REF_ONLY**.</span></span> <span data-ttu-id="592d7-137">与**ATTACH_BY_REF_RESOLVE**，绝对路径快，原因是 MAPI 后台处理程序将转换为**ATTACH_BY_VALUE**附件。</span><span class="sxs-lookup"><span data-stu-id="592d7-137">With **ATTACH_BY_REF_RESOLVE**, an absolute path is faster, because the MAPI spooler converts the attachment to **ATTACH_BY_VALUE**.</span></span> 
  
<span data-ttu-id="592d7-138">如果设置**ATTACH_BY_REFERENCE** ， **PR_ATTACH_DATA_BIN**必须为空。</span><span class="sxs-lookup"><span data-stu-id="592d7-138">If **ATTACH_BY_REFERENCE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="592d7-139">出站的网关可以通过将附件数据复制到**PR_ATTACH_DATA_BIN**属性打开到**ATTACH_BY_VALUE**附件**ATTACH_BY_REFERENCE**附件。</span><span class="sxs-lookup"><span data-stu-id="592d7-139">An outbound gateway can turn an **ATTACH_BY_REFERENCE** attachment into an **ATTACH_BY_VALUE** attachment by copying the attachment data into the **PR_ATTACH_DATA_BIN** property.</span></span> 
  
<span data-ttu-id="592d7-140">如果设置**ATTACH_BY_REF_RESOLVE** ， **PR_ATTACH_DATA_BIN**必须为空。</span><span class="sxs-lookup"><span data-stu-id="592d7-140">If **ATTACH_BY_REF_RESOLVE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="592d7-141">当发送包含**ATTACH_BY_REF_RESOLVE**附件的邮件时，MAPI 后台处理程序会将附件数据复制到**ATTACH_BY_VALUE**附件。</span><span class="sxs-lookup"><span data-stu-id="592d7-141">When the message that contains the **ATTACH_BY_REF_RESOLVE** attachment is sent, the MAPI spooler copies the attachment data into an **ATTACH_BY_VALUE** attachment.</span></span> <span data-ttu-id="592d7-142">此解决方案过程置于**PR_ATTACH_DATA_BIN**附件数据。</span><span class="sxs-lookup"><span data-stu-id="592d7-142">This resolution process places the attachment data in **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="592d7-143">如果设置**ATTACH_BY_REF_ONLY** ， **PR_ATTACH_DATA_BIN**必须为空，并且将在邮件系统从不解析附件参考 （英文）。</span><span class="sxs-lookup"><span data-stu-id="592d7-143">If **ATTACH_BY_REF_ONLY** is set, **PR_ATTACH_DATA_BIN** must be empty, and the messaging system never resolves the attachment reference.</span></span> <span data-ttu-id="592d7-144">您想要发送的链接，但不是数据时，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="592d7-144">Use this value when you want to send the link but not the data.</span></span> 
  
<span data-ttu-id="592d7-145">OLE 2.0 **IStorage**格式 OLE 对象时，数据是可通过**PR_ATTACH_DATA_OBJ**访问。</span><span class="sxs-lookup"><span data-stu-id="592d7-145">When the OLE object is in OLE 2.0 **IStorage** format, the data is accessible through **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="592d7-146">OLE 1.0 **OLESTREAM**格式 OLE 对象时，则可以为**IStream**可通过**PR_ATTACH_DATA_BIN**访问数据。</span><span class="sxs-lookup"><span data-stu-id="592d7-146">When the OLE object is in OLE 1.0 **OLESTREAM** format, the data is accessible through **PR_ATTACH_DATA_BIN** as an **IStream**.</span></span> <span data-ttu-id="592d7-147">可以通过**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 值确定的 OLE 编码类型。</span><span class="sxs-lookup"><span data-stu-id="592d7-147">The type of the OLE encoding can be determined by the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) value.</span></span> 
  
<span data-ttu-id="592d7-148">OLE 接口和格式的详细信息，请参阅*OLE 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="592d7-148">For more information on OLE interfaces and formats, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="592d7-149">备注</span><span class="sxs-lookup"><span data-stu-id="592d7-149">Remarks</span></span>

<span data-ttu-id="592d7-150">**ATTACH_BY_WEBREFERENCE** **PR_ATTACH_METHOD**后，附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="592d7-150">When the **PR_ATTACH_METHOD** is **ATTACH_BY_WEBREFERENCE**, the attachment content is not in the message.</span></span> <span data-ttu-id="592d7-151">相反，则**PR_ATTACH_LONG_FILENAME**属性包含附件内容，联机存储的绝对 URL。</span><span class="sxs-lookup"><span data-stu-id="592d7-151">Instead, the **PR_ATTACH_LONG_FILENAME** property contains an absolute URL to the attachment content, which is stored online.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="592d7-152">相关资源</span><span class="sxs-lookup"><span data-stu-id="592d7-152">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="592d7-153">协议规范</span><span class="sxs-lookup"><span data-stu-id="592d7-153">Protocol specifications</span></span>

<span data-ttu-id="592d7-154">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="592d7-154">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="592d7-155">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="592d7-155">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="592d7-156">头文件</span><span class="sxs-lookup"><span data-stu-id="592d7-156">Header files</span></span>

<span data-ttu-id="592d7-157">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="592d7-157">Mapidefs.h</span></span>
  
> <span data-ttu-id="592d7-158">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="592d7-158">Provides data type definitions.</span></span>
    
<span data-ttu-id="592d7-159">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="592d7-159">Mapitags.h</span></span>
  
> <span data-ttu-id="592d7-160">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="592d7-160">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="592d7-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="592d7-161">See also</span></span>



[<span data-ttu-id="592d7-162">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="592d7-162">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)


[<span data-ttu-id="592d7-163">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="592d7-163">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="592d7-164">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="592d7-164">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="592d7-165">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="592d7-165">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="592d7-166">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="592d7-166">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

