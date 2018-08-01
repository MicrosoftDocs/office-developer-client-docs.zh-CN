---
title: PidTagAttachFilename 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachFilename
api_type:
- HeaderDef
ms.assetid: cbf34dd6-7733-47f6-9c41-9d82656ca9dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4468ecd5946c95fab62d0885d9c0b3343a1508dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777346"
---
# <a name="pidtagattachfilename-canonical-property"></a><span data-ttu-id="d4235-103">PidTagAttachFilename 规范属性</span><span class="sxs-lookup"><span data-stu-id="d4235-103">PidTagAttachFilename Canonical Property</span></span>

  
  
<span data-ttu-id="d4235-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d4235-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d4235-105">包含附件的基文件名和扩展名，不包括路径。</span><span class="sxs-lookup"><span data-stu-id="d4235-105">Contains an attachment's base file name and extension, excluding path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d4235-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d4235-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d4235-107">PR_ATTACH_FILENAME，PR_ATTACH_FILENAME_A，PR_ATTACH_FILENAME_W</span><span class="sxs-lookup"><span data-stu-id="d4235-107">PR_ATTACH_FILENAME, PR_ATTACH_FILENAME_A, PR_ATTACH_FILENAME_W</span></span>  <br/> |
|<span data-ttu-id="d4235-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="d4235-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d4235-109">0x3704</span><span class="sxs-lookup"><span data-stu-id="d4235-109">0x3704</span></span>  <br/> |
|<span data-ttu-id="d4235-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d4235-110">Data type:</span></span>  <br/> |<span data-ttu-id="d4235-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d4235-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="d4235-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d4235-112">Area:</span></span>  <br/> |<span data-ttu-id="d4235-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="d4235-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d4235-114">说明</span><span class="sxs-lookup"><span data-stu-id="d4235-114">Remarks</span></span>

<span data-ttu-id="d4235-115">建议 attachment 对象公开的**PR_ATTACH_METHOD** **ATTACH_BY_VALUE**、 **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**和**ATTACH_BY_REF_ONLY**值与这些属性([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d4235-115">It is recommended that attachment objects expose these properties which pertain to the **ATTACH_BY_VALUE**, **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, and **ATTACH_BY_REF_ONLY** values of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span> <span data-ttu-id="d4235-116">**PR_ATTACH_FILENAME**和关联的属性所需时使用以下任一值。</span><span class="sxs-lookup"><span data-stu-id="d4235-116">**PR_ATTACH_FILENAME** and associated properties are required when any of these values is used.</span></span> 
  
<span data-ttu-id="d4235-117">这些属性可用作建议的文件名保存附件并提供的文件扩展名，如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d4235-117">These properties can be used as a suggested file name for saving the attachment and to supply the file name extension if the **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) property is not provided.</span></span> 
  
<span data-ttu-id="d4235-118">限制为八个字符扩展名为三个字符的文件名称。</span><span class="sxs-lookup"><span data-stu-id="d4235-118">The file name is restricted to eight characters plus a three-character extension.</span></span> <span data-ttu-id="d4235-119">支持长文件名的平台，将设置此属性和**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d4235-119">For a platform that supports long file names, set both this property and the **PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="d4235-120">MAPI 仅适用于文件的名称，并在其他字符串传递给它，协会 (ANSI) 字符集中。</span><span class="sxs-lookup"><span data-stu-id="d4235-120">MAPI works only with file names, and other strings passed to it, in the American National Standards Institute (ANSI) character set.</span></span> <span data-ttu-id="d4235-121">使用文件名的原始设备制造商 (OEM) 字符集中的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="d4235-121">Client applications that use file names in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d4235-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="d4235-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d4235-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="d4235-123">Protocol specifications</span></span>

<span data-ttu-id="d4235-124">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4235-124">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d4235-125">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="d4235-125">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="d4235-126">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4235-126">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d4235-127">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="d4235-127">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="d4235-128">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4235-128">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d4235-129">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="d4235-129">Specifies the properties of rights-managed encoded messages.</span></span>
    
<span data-ttu-id="d4235-130">[[MS OXOSMIME]](http://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4235-130">[[MS-OXOSMIME]](http://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d4235-131">指定 S/MIME 签名和加密的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="d4235-131">Specifies S/MIME signed and encrypted message properties.</span></span>
    
<span data-ttu-id="d4235-132">[[MS OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d4235-132">[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d4235-133">进行编码和解码为有效的流表示形式的消息和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d4235-133">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d4235-134">头文件</span><span class="sxs-lookup"><span data-stu-id="d4235-134">Header files</span></span>

<span data-ttu-id="d4235-135">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d4235-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="d4235-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d4235-136">Provides data type definitions.</span></span>
    
<span data-ttu-id="d4235-137">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d4235-137">Mapitags.h</span></span>
  
> <span data-ttu-id="d4235-138">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d4235-138">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d4235-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4235-139">See also</span></span>



[<span data-ttu-id="d4235-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d4235-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d4235-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d4235-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d4235-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d4235-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d4235-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d4235-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

