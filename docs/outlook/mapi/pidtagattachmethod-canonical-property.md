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
description: 上次修改时间：2016 年 9 月 7 日
ms.openlocfilehash: b84549ab31c939b4e6115795916ebd3520a96dbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327256"
---
# <a name="pidtagattachmethod-canonical-property"></a><span data-ttu-id="a619b-103">PidTagAttachMethod 规范属性</span><span class="sxs-lookup"><span data-stu-id="a619b-103">PidTagAttachMethod Canonical Property</span></span>

 
  
<span data-ttu-id="a619b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a619b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a619b-105">包含一个 MAPI 定义的常量，该常量代表可以访问附件内容的方式。</span><span class="sxs-lookup"><span data-stu-id="a619b-105">Contains a MAPI-defined constant representing the way the contents of an attachment can be accessed.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a619b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a619b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a619b-107">PR_ATTACH_METHOD</span><span class="sxs-lookup"><span data-stu-id="a619b-107">PR_ATTACH_METHOD</span></span>  <br/> |
|<span data-ttu-id="a619b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a619b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a619b-109">0x3705</span><span class="sxs-lookup"><span data-stu-id="a619b-109">0x3705</span></span>  <br/> |
|<span data-ttu-id="a619b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a619b-110">Data type:</span></span>  <br/> |<span data-ttu-id="a619b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="a619b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="a619b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a619b-112">Area:</span></span>  <br/> |<span data-ttu-id="a619b-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="a619b-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a619b-114">备注</span><span class="sxs-lookup"><span data-stu-id="a619b-114">Remarks</span></span>

<span data-ttu-id="a619b-115">此属性可以正好具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="a619b-115">This property can have exactly one of the following values:</span></span>
  
<span data-ttu-id="a619b-116">NO_ATTACHMENT</span><span class="sxs-lookup"><span data-stu-id="a619b-116">NO_ATTACHMENT</span></span> 
  
> <span data-ttu-id="a619b-117">附件刚刚创建。</span><span class="sxs-lookup"><span data-stu-id="a619b-117">The attachment has just been created.</span></span> 
    
<span data-ttu-id="a619b-118">ATTACH_BY_VALUE</span><span class="sxs-lookup"><span data-stu-id="a619b-118">ATTACH_BY_VALUE</span></span> 
  
> <span data-ttu-id="a619b-119">[PidTagAttachDataBinary PR_ATTACH_DATA_BIN (PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 包含附件数据。 </span><span class="sxs-lookup"><span data-stu-id="a619b-119">The **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property contains the attachment data.</span></span> 
    
<span data-ttu-id="a619b-120">ATTACH_BY_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="a619b-120">ATTACH_BY_REFERENCE</span></span> 
  
> <span data-ttu-id="a619b-121">PR_ATTACH_PATHNAME ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或 **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含一个完全限定的路径，该路径标识具有公用文件服务器访问权限的收件人的附件。 </span><span class="sxs-lookup"><span data-stu-id="a619b-121">The **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) or **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) property contains a fully-qualified path identifying the attachment to recipients with access to a common file server.</span></span> 
    
<span data-ttu-id="a619b-122">ATTACH_BY_REF_RESOLVE</span><span class="sxs-lookup"><span data-stu-id="a619b-122">ATTACH_BY_REF_RESOLVE</span></span> 
  
> <span data-ttu-id="a619b-123">PR_ATTACH_PATHNAME 或 **PR_ATTACH_LONG_PATHNAME** 属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="a619b-123">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="a619b-124">ATTACH_BY_REF_ONLY</span><span class="sxs-lookup"><span data-stu-id="a619b-124">ATTACH_BY_REF_ONLY</span></span> 
  
> <span data-ttu-id="a619b-125">PR_ATTACH_PATHNAME 或 **PR_ATTACH_LONG_PATHNAME** 属性包含标识附件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="a619b-125">The **PR_ATTACH_PATHNAME** or **PR_ATTACH_LONG_PATHNAME** property contains a fully-qualified path identifying the attachment.</span></span> 
    
<span data-ttu-id="a619b-126">ATTACH_EMBEDDED_MSG</span><span class="sxs-lookup"><span data-stu-id="a619b-126">ATTACH_EMBEDDED_MSG</span></span> 
  
> <span data-ttu-id="a619b-127">The **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property contains an embedded object that supports the **IMessage** interface.</span><span class="sxs-lookup"><span data-stu-id="a619b-127">The **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property contains an embedded object that supports the **IMessage** interface.</span></span> 
    
<span data-ttu-id="a619b-128">ATTACH_OLE</span><span class="sxs-lookup"><span data-stu-id="a619b-128">ATTACH_OLE</span></span> 
  
> <span data-ttu-id="a619b-129">附件是一个嵌入的 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="a619b-129">The attachment is an embedded OLE object.</span></span>
    
<span data-ttu-id="a619b-130">ATTACH_BY_WEBREFERENCE</span><span class="sxs-lookup"><span data-stu-id="a619b-130">ATTACH_BY_WEBREFERENCE</span></span> 
  
> <span data-ttu-id="a619b-131">附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="a619b-131">The attachment content is not in the message.</span></span> 
    
<span data-ttu-id="a619b-132">创建后，所有 attachment 对象的初始 **PR_ATTACH_METHOD值为\*\*\*\*NO_ATTACHMENT**。</span><span class="sxs-lookup"><span data-stu-id="a619b-132">When created, all attachment objects have an initial **PR_ATTACH_METHOD** value of **NO_ATTACHMENT**.</span></span> 
  
<span data-ttu-id="a619b-133">客户端应用程序和服务提供商只需要支持由值表示的 attachment **ATTACH_BY_VALUE方法。**</span><span class="sxs-lookup"><span data-stu-id="a619b-133">Client applications and service providers are only required to support the attachment method represented by the **ATTACH_BY_VALUE** value.</span></span> <span data-ttu-id="a619b-134">其他附件方法是可选的。</span><span class="sxs-lookup"><span data-stu-id="a619b-134">The other attachment methods are optional.</span></span> <span data-ttu-id="a619b-135">邮件存储不会强制在 PR_ATTACH_METHOD **和其他附件** 属性的值之间保持一致。</span><span class="sxs-lookup"><span data-stu-id="a619b-135">The message store does not enforce any consistency between the value of **PR_ATTACH_METHOD** and the values of the other attachment properties.</span></span> 
  
<span data-ttu-id="a619b-136">建议完全限定 (UNC) 名称的通用命名约定，该路径应该与 ATTACH_BY_REFERENCE **和\*\*\*\*ATTACH_BY_REF_ONLY 一ATTACH_BY_REF_ONLY。**</span><span class="sxs-lookup"><span data-stu-id="a619b-136">Universal naming convention (UNC) names are recommended for fully-qualified paths, which should be used with **ATTACH_BY_REFERENCE** and **ATTACH_BY_REF_ONLY**.</span></span> <span data-ttu-id="a619b-137">使用 **ATTACH_BY_REF_RESOLVE，** 绝对路径速度更快，因为 MAPI 后台处理程序会将 **附件转换为** ATTACH_BY_VALUE。</span><span class="sxs-lookup"><span data-stu-id="a619b-137">With **ATTACH_BY_REF_RESOLVE**, an absolute path is faster, because the MAPI spooler converts the attachment to **ATTACH_BY_VALUE**.</span></span> 
  
<span data-ttu-id="a619b-138">如果 **ATTACH_BY_REFERENCE，** 则 **PR_ATTACH_DATA_BIN** 必须为空。</span><span class="sxs-lookup"><span data-stu-id="a619b-138">If **ATTACH_BY_REFERENCE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="a619b-139">出站网关可以通过将ATTACH_BY_REFERENCE数据复制到 ATTACH_BY_VALUE **属性，** 将邮件附件转换为 **PR_ATTACH_DATA_BIN附件。**</span><span class="sxs-lookup"><span data-stu-id="a619b-139">An outbound gateway can turn an **ATTACH_BY_REFERENCE** attachment into an **ATTACH_BY_VALUE** attachment by copying the attachment data into the **PR_ATTACH_DATA_BIN** property.</span></span> 
  
<span data-ttu-id="a619b-140">如果 **ATTACH_BY_REF_RESOLVE，** 则 **PR_ATTACH_DATA_BIN** 必须为空。</span><span class="sxs-lookup"><span data-stu-id="a619b-140">If **ATTACH_BY_REF_RESOLVE** is set, **PR_ATTACH_DATA_BIN** must be empty.</span></span> <span data-ttu-id="a619b-141">发送包含附件附件ATTACH_BY_REF_RESOLVE，MAPI 后台处理程序将附件数据复制到一个 **ATTACH_BY_VALUE附件。** </span><span class="sxs-lookup"><span data-stu-id="a619b-141">When the message that contains the **ATTACH_BY_REF_RESOLVE** attachment is sent, the MAPI spooler copies the attachment data into an **ATTACH_BY_VALUE** attachment.</span></span> <span data-ttu-id="a619b-142">此解决方案过程将附件 **数据PR_ATTACH_DATA_BIN。**</span><span class="sxs-lookup"><span data-stu-id="a619b-142">This resolution process places the attachment data in **PR_ATTACH_DATA_BIN**.</span></span> 
  
<span data-ttu-id="a619b-143">如果 **ATTACH_BY_REF_ONLY，PR_ATTACH_DATA_BIN** 必须为空，并且邮件系统从不解析附件引用。</span><span class="sxs-lookup"><span data-stu-id="a619b-143">If **ATTACH_BY_REF_ONLY** is set, **PR_ATTACH_DATA_BIN** must be empty, and the messaging system never resolves the attachment reference.</span></span> <span data-ttu-id="a619b-144">当你想要发送链接而不是数据时，请使用此值。</span><span class="sxs-lookup"><span data-stu-id="a619b-144">Use this value when you want to send the link but not the data.</span></span> 
  
<span data-ttu-id="a619b-145">当 OLE 对象采用 OLE 2.0 **IStorage** 格式时，可通过 PR_ATTACH_DATA_OBJ 访问 **数据**。</span><span class="sxs-lookup"><span data-stu-id="a619b-145">When the OLE object is in OLE 2.0 **IStorage** format, the data is accessible through **PR_ATTACH_DATA_OBJ**.</span></span> <span data-ttu-id="a619b-146">当 OLE 对象采用 OLE 1.0 **OLESTREAM** 格式时，可通过 **IStream PR_ATTACH_DATA_BIN访问数据**。</span><span class="sxs-lookup"><span data-stu-id="a619b-146">When the OLE object is in OLE 1.0 **OLESTREAM** format, the data is accessible through **PR_ATTACH_DATA_BIN** as an **IStream**.</span></span> <span data-ttu-id="a619b-147">OLE 编码的类型可以通过[PidTagAttachTag PR_ATTACH_TAG (PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定。 </span><span class="sxs-lookup"><span data-stu-id="a619b-147">The type of the OLE encoding can be determined by the **PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) value.</span></span> 
  
<span data-ttu-id="a619b-148">有关 OLE 接口和格式的信息，请参阅 *《OLE 程序员参考》。*</span><span class="sxs-lookup"><span data-stu-id="a619b-148">For more information on OLE interfaces and formats, see the  *OLE Programmer's Reference*  .</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a619b-149">备注</span><span class="sxs-lookup"><span data-stu-id="a619b-149">Remarks</span></span>

<span data-ttu-id="a619b-150">当 **PR_ATTACH_METHOD** 时 **ATTACH_BY_WEBREFERENCE，** 附件内容不在邮件中。</span><span class="sxs-lookup"><span data-stu-id="a619b-150">When the **PR_ATTACH_METHOD** is **ATTACH_BY_WEBREFERENCE**, the attachment content is not in the message.</span></span> <span data-ttu-id="a619b-151">相反 **，PR_ATTACH_LONG_FILENAME** 属性包含指向联机存储的附件内容的绝对 URL。</span><span class="sxs-lookup"><span data-stu-id="a619b-151">Instead, the **PR_ATTACH_LONG_FILENAME** property contains an absolute URL to the attachment content, which is stored online.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a619b-152">相关资源</span><span class="sxs-lookup"><span data-stu-id="a619b-152">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a619b-153">协议规范</span><span class="sxs-lookup"><span data-stu-id="a619b-153">Protocol specifications</span></span>

<span data-ttu-id="a619b-154">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a619b-154">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a619b-155">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a619b-155">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a619b-156">头文件</span><span class="sxs-lookup"><span data-stu-id="a619b-156">Header files</span></span>

<span data-ttu-id="a619b-157">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a619b-157">Mapidefs.h</span></span>
  
> <span data-ttu-id="a619b-158">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a619b-158">Provides data type definitions.</span></span>
    
<span data-ttu-id="a619b-159">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a619b-159">Mapitags.h</span></span>
  
> <span data-ttu-id="a619b-160">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a619b-160">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a619b-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a619b-161">See also</span></span>



[<span data-ttu-id="a619b-162">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="a619b-162">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)


[<span data-ttu-id="a619b-163">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a619b-163">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a619b-164">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a619b-164">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a619b-165">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a619b-165">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a619b-166">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a619b-166">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

