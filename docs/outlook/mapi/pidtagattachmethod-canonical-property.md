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
description: 上次修改时间:07 年9月2016
ms.openlocfilehash: b84549ab31c939b4e6115795916ebd3520a96dbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327256"
---
# <a name="pidtagattachmethod-canonical-property"></a><span data-ttu-id="8aa22-103">PidTagAttachMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="8aa22-103">PidTagAttachMethod Canonical Property</span></span>

 
  
<span data-ttu-id="8aa22-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8aa22-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8aa22-105">包含一个 MAPI 定义的常量, 该常量代表可访问附件内容的方式。</span><span class="sxs-lookup"><span data-stu-id="8aa22-105">Contains a MAPI-defined constant representing the way the contents of an attachment can be accessed.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8aa22-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8aa22-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8aa22-107">PR_ATTACH_METHOD</span><span class="sxs-lookup"><span data-stu-id="8aa22-107">PR_ATTACH_METHOD</span></span>  <br/> |
|<span data-ttu-id="8aa22-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8aa22-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8aa22-109">0x3705</span><span class="sxs-lookup"><span data-stu-id="8aa22-109">0x3705</span></span>  <br/> |
|<span data-ttu-id="8aa22-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8aa22-110">Data type:</span></span>  <br/> |<span data-ttu-id="8aa22-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8aa22-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8aa22-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8aa22-112">Area:</span></span>  <br/> |<span data-ttu-id="8aa22-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="8aa22-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8aa22-114">注解</span><span class="sxs-lookup"><span data-stu-id="8aa22-114">Remarks</span></span>

<span data-ttu-id="8aa22-115">此属性可以具有下列值之一:</span><span class="sxs-lookup"><span data-stu-id="8aa22-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="8aa22-116">NO_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="8aa22-116">NO_ATTACHMENT</span></span> 
  
> <span data-ttu-id="8aa22-117">附件刚刚创建。</span><span class="sxs-lookup"><span data-stu-id="8aa22-117">The attachment has just been created.</span></span> 
    
<span data-ttu-id="8aa22-118">ATTACH_BY_VALUE</span><span class="sxs-lookup"><span data-stu-id="8aa22-118">ATTACH_BY_VALUE</span></span> 
  
> <span data-ttu-id="8aa22-119">**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性包含附件数据。</span><span class="sxs-lookup"><span data-stu-id="8aa22-119">The **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property contains the attachment data.</span></span> 
    
<span data-ttu-id="8aa22-120">ATTACH_BY_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="8aa22-120">ATTACH_BY_REFERENCE</span></span> 
  
> <span data-ttu-id="8aa22-121">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含一个完全限定路径, 用于标识收件人可访问公用文件的附件服务器主板.</span><span class="sxs-lookup"><span data-stu-id="8aa22-121">The **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) or **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) property contains a fully-qualified path identifying the attachment to recipients with access to a common file server.</span></span> 
    
<span data-ttu-id="8aa22-122">ATTACH_BY_REF_RESOLVE</span><span class="sxs-lookup"><span data-stu-id="8aa22-122">ATTACH_BY_REF_RESOLVE</span></span> 
  
> <span data-ttu-id="8aa22-123">**PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="8aa22-123">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="8aa22-124">ATTACH_BY_REF_ONLY</span><span class="sxs-lookup"><span data-stu-id="8aa22-124">ATTACH_BY_REF_ONLY</span></span> 
  
> <span data-ttu-id="8aa22-125">**PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="8aa22-125">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="8aa22-126">ATTACH_EMBEDDED_MSG</span><span class="sxs-lookup"><span data-stu-id="8aa22-126">ATTACH_EMBEDDED_MSG</span></span> 
  
> <span data-ttu-id="8aa22-127">**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性包含一个支持**IMessage**接口的嵌入对象。</span><span class="sxs-lookup"><span data-stu-id="8aa22-127">The **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property contains an embedded object that supports the **IMessage** interface.</span></span> 
    
<span data-ttu-id="8aa22-128">ATTACH_OLE</span><span class="sxs-lookup"><span data-stu-id="8aa22-128">ATTACH_OLE</span></span> 
  
> <span data-ttu-id="8aa22-129">附件是嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="8aa22-129">The attachment is an embedded OLE object.</span></span>
    
<span data-ttu-id="8aa22-130">ATTACH_BY_WEBREFERENCE</span><span class="sxs-lookup"><span data-stu-id="8aa22-130">ATTACH_BY_WEBREFERENCE</span></span> 
  
> <span data-ttu-id="8aa22-131">附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="8aa22-131">The attachment content is not in the message.</span></span> 
    
<span data-ttu-id="8aa22-132">创建后, 所有附件对象的初始**PR_ATTACH_METHOD**值均为**NO_ATTACHMENT**。</span><span class="sxs-lookup"><span data-stu-id="8aa22-132">When created, all attachment objects have an initial **PR_ATTACH_METHOD** value of **NO_ATTACHMENT**.</span></span> 
  
<span data-ttu-id="8aa22-133">客户端应用程序和服务提供程序只需支持**ATTACH_BY_VALUE**值所表示的附件方法。</span><span class="sxs-lookup"><span data-stu-id="8aa22-133">Client applications and service providers are only required to support the attachment method represented by the **ATTACH_BY_VALUE** value.</span></span> <span data-ttu-id="8aa22-134">其他附件方法是可选的。</span><span class="sxs-lookup"><span data-stu-id="8aa22-134">The other attachment methods are optional.</span></span> <span data-ttu-id="8aa22-135">邮件存储不强制**PR_ATTACH_METHOD**的值与其他附件属性的值之间的一致性。</span><span class="sxs-lookup"><span data-stu-id="8aa22-135">The message store does not enforce any consistency between the value of **PR_ATTACH_METHOD** and the values of the other attachment properties.</span></span> 
  
<span data-ttu-id="8aa22-136">对于完全限定的路径, 建议使用通用命名约定 (UNC) 名称, 该名称应与**ATTACH_BY_REFERENCE**和**ATTACH_BY_REF_ONLY**一起使用。</span><span class="sxs-lookup"><span data-stu-id="8aa22-136">Universal naming convention (UNC) names are recommended for fully-qualified paths, which should be used with **ATTACH_BY_REFERENCE** and **ATTACH_BY_REF_ONLY**.</span></span> <span data-ttu-id="8aa22-137">使用**ATTACH_BY_REF_RESOLVE**, 绝对路径速度更快, 因为 MAPI 后台处理程序将附件转换为**ATTACH_BY_VALUE**。</span><span class="sxs-lookup"><span data-stu-id="8aa22-137">With **ATTACH_BY_REF_RESOLVE**, an absolute path is faster, because the MAPI spooler converts the attachment to **ATTACH_BY_VALUE**.</span></span> 
  
<span data-ttu-id="8aa22-138">如果设置了**ATTACH_BY_REFERENCE** , 则**PR_ATTACH_DATA_BIN**必须为空。</span><span class="sxs-lookup"><span data-stu-id="8aa22-138">If **ATTACH_BY_REFERENCE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="8aa22-139">出站网关可以通过将附件数据复制到**PR_ATTACH_DATA_BIN**属性, 将**ATTACH_BY_REFERENCE**附件转换为**ATTACH_BY_VALUE**附件。</span><span class="sxs-lookup"><span data-stu-id="8aa22-139">An outbound gateway can turn an **ATTACH_BY_REFERENCE** attachment into an **ATTACH_BY_VALUE** attachment by copying the attachment data into the **PR_ATTACH_DATA_BIN** property.</span></span> 
  
<span data-ttu-id="8aa22-140">如果设置了**ATTACH_BY_REF_RESOLVE** , 则**PR_ATTACH_DATA_BIN**必须为空。</span><span class="sxs-lookup"><span data-stu-id="8aa22-140">If **ATTACH_BY_REF_RESOLVE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="8aa22-141">当发送包含**ATTACH_BY_REF_RESOLVE**附件的邮件时, MAPI 后台处理程序会将附件数据复制到**ATTACH_BY_VALUE**附件中。</span><span class="sxs-lookup"><span data-stu-id="8aa22-141">When the message that contains the **ATTACH_BY_REF_RESOLVE** attachment is sent, the MAPI spooler copies the attachment data into an **ATTACH_BY_VALUE** attachment.</span></span> <span data-ttu-id="8aa22-142">此解析过程将附件数据放在**PR_ATTACH_DATA_BIN**中。</span><span class="sxs-lookup"><span data-stu-id="8aa22-142">This resolution process places the attachment data in **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="8aa22-143">如果设置了**ATTACH_BY_REF_ONLY** , 则**PR_ATTACH_DATA_BIN**必须为空, 并且邮件系统永远不会解析附件引用。</span><span class="sxs-lookup"><span data-stu-id="8aa22-143">If **ATTACH_BY_REF_ONLY** is set, **PR_ATTACH_DATA_BIN** must be empty, and the messaging system never resolves the attachment reference.</span></span> <span data-ttu-id="8aa22-144">如果要发送链接, 而不是数据, 则使用此值。</span><span class="sxs-lookup"><span data-stu-id="8aa22-144">Use this value when you want to send the link but not the data.</span></span> 
  
<span data-ttu-id="8aa22-145">如果 ole 对象采用的是 ole 2.0 **IStorage**格式, 则可以通过**PR_ATTACH_DATA_OBJ**访问该数据。</span><span class="sxs-lookup"><span data-stu-id="8aa22-145">When the OLE object is in OLE 2.0 **IStorage** format, the data is accessible through **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="8aa22-146">如果 ole 对象采用的是 ole 1.0 **OLESTREAM**格式, 则可以通过**PR_ATTACH_DATA_BIN**作为**IStream**访问数据。</span><span class="sxs-lookup"><span data-stu-id="8aa22-146">When the OLE object is in OLE 1.0 **OLESTREAM** format, the data is accessible through **PR_ATTACH_DATA_BIN** as an **IStream**.</span></span> <span data-ttu-id="8aa22-147">可以通过**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 值确定 OLE 编码的类型。</span><span class="sxs-lookup"><span data-stu-id="8aa22-147">The type of the OLE encoding can be determined by the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) value.</span></span> 
  
<span data-ttu-id="8aa22-148">有关 ole 接口和格式的详细信息, 请参阅*ole 程序员参考*。</span><span class="sxs-lookup"><span data-stu-id="8aa22-148">For more information on OLE interfaces and formats, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8aa22-149">注解</span><span class="sxs-lookup"><span data-stu-id="8aa22-149">Remarks</span></span>

<span data-ttu-id="8aa22-150">当**PR_ATTACH_METHOD**为**ATTACH_BY_WEBREFERENCE**时, 附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="8aa22-150">When the **PR_ATTACH_METHOD** is **ATTACH_BY_WEBREFERENCE**, the attachment content is not in the message.</span></span> <span data-ttu-id="8aa22-151">相反, **PR_ATTACH_LONG_FILENAME**属性包含附件内容的绝对 URL, 该 URL 存储在联机状态。</span><span class="sxs-lookup"><span data-stu-id="8aa22-151">Instead, the **PR_ATTACH_LONG_FILENAME** property contains an absolute URL to the attachment content, which is stored online.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8aa22-152">相关资源</span><span class="sxs-lookup"><span data-stu-id="8aa22-152">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8aa22-153">协议规范</span><span class="sxs-lookup"><span data-stu-id="8aa22-153">Protocol specifications</span></span>

<span data-ttu-id="8aa22-154">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8aa22-154">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8aa22-155">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="8aa22-155">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8aa22-156">头文件</span><span class="sxs-lookup"><span data-stu-id="8aa22-156">Header files</span></span>

<span data-ttu-id="8aa22-157">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8aa22-157">Mapidefs.h</span></span>
  
> <span data-ttu-id="8aa22-158">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8aa22-158">Provides data type definitions.</span></span>
    
<span data-ttu-id="8aa22-159">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8aa22-159">Mapitags.h</span></span>
  
> <span data-ttu-id="8aa22-160">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8aa22-160">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8aa22-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8aa22-161">See also</span></span>



[<span data-ttu-id="8aa22-162">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="8aa22-162">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)


[<span data-ttu-id="8aa22-163">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8aa22-163">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8aa22-164">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8aa22-164">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8aa22-165">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8aa22-165">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8aa22-166">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8aa22-166">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

