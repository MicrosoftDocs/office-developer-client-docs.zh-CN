---
title: PidTagAttachPathname 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachPathname
api_type:
- HeaderDef
ms.assetid: e19c7cd1-7c56-4f63-8736-d6971c7c5f4d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b7e0c174f0b31522cffbb4761ab64a50267874be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777359"
---
# <a name="pidtagattachpathname-canonical-property"></a><span data-ttu-id="41061-103">PidTagAttachPathname 规范属性</span><span class="sxs-lookup"><span data-stu-id="41061-103">PidTagAttachPathname Canonical Property</span></span>

  
  
<span data-ttu-id="41061-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="41061-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="41061-105">包含附件的完全限定路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="41061-105">Contains an attachment's fully-qualified path and filename.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="41061-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="41061-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="41061-107">PR_ATTACH_PATHNAME，PR_ATTACH_PATHNAME_A，PR_ATTACH_PATHNAME_W</span><span class="sxs-lookup"><span data-stu-id="41061-107">PR_ATTACH_PATHNAME, PR_ATTACH_PATHNAME_A, PR_ATTACH_PATHNAME_W</span></span>  <br/> |
|<span data-ttu-id="41061-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="41061-108">Identifier:</span></span>  <br/> |<span data-ttu-id="41061-109">0x3708</span><span class="sxs-lookup"><span data-stu-id="41061-109">0x3708</span></span>  <br/> |
|<span data-ttu-id="41061-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="41061-110">Data type:</span></span>  <br/> |<span data-ttu-id="41061-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="41061-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="41061-112">区域：</span><span class="sxs-lookup"><span data-stu-id="41061-112">Area:</span></span>  <br/> |<span data-ttu-id="41061-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="41061-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="41061-114">备注</span><span class="sxs-lookup"><span data-stu-id="41061-114">Remarks</span></span>

<span data-ttu-id="41061-115">建议附件子对象公开这些属性。</span><span class="sxs-lookup"><span data-stu-id="41061-115">It is recommended that attachment subobjects expose these properties.</span></span> <span data-ttu-id="41061-116">它们设置指示附件数据不包含在邮件，但在常见的文件服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="41061-116">Setting them indicates that the attachment data is not included with the message but is available on a common file server.</span></span> <span data-ttu-id="41061-117">这些属性所需引用连同任何**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 标志指示附件： **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**或**ATTACH_BY_REF_仅**。</span><span class="sxs-lookup"><span data-stu-id="41061-117">These properties are required in conjunction with any of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) flags that indicate attachment by reference: **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, or **ATTACH_BY_REF_ONLY**.</span></span> 
  
<span data-ttu-id="41061-118">每个目录或文件名仅限于八个字符的名称扩展名为三个字符。</span><span class="sxs-lookup"><span data-stu-id="41061-118">Each directory or filename is restricted to an eight-character name plus a three-character extension.</span></span> <span data-ttu-id="41061-119">限制为 256 个字符的总体路径。</span><span class="sxs-lookup"><span data-stu-id="41061-119">The overall path is restricted to 256 characters.</span></span> <span data-ttu-id="41061-120">支持长文件名的平台，将设置这些属性和**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="41061-120">For a platform that supports long filenames, set both these properties and **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)).</span></span> 
  
<span data-ttu-id="41061-121">文件共享，以及本地文件时，应使用绝对路径时，客户端应用程序应在大多数情况下使用通用命名约定 (UNC)。</span><span class="sxs-lookup"><span data-stu-id="41061-121">Client applications should use a universal naming convention (UNC) in most cases when the file is shared, and should use an absolute path when the file is local.</span></span>
  
<span data-ttu-id="41061-122">MAPI 仅适用于路径和文件名 ansi 字符集。</span><span class="sxs-lookup"><span data-stu-id="41061-122">MAPI works only with paths and filenames in the ANSI character set.</span></span> <span data-ttu-id="41061-123">使用 OEM 字符集中的路径和文件名的客户端必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="41061-123">Clients that use paths and filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="41061-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="41061-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="41061-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="41061-125">Protocol specifications</span></span>

<span data-ttu-id="41061-126">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="41061-126">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="41061-127">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="41061-127">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="41061-128">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="41061-128">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="41061-129">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="41061-129">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="41061-130">头文件</span><span class="sxs-lookup"><span data-stu-id="41061-130">Header files</span></span>

<span data-ttu-id="41061-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="41061-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="41061-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="41061-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="41061-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="41061-133">Mapitags.h</span></span>
  
> <span data-ttu-id="41061-134">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="41061-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="41061-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41061-135">See also</span></span>



[<span data-ttu-id="41061-136">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="41061-136">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)
  
[<span data-ttu-id="41061-137">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="41061-137">ScUNCFromLocalPath</span></span>](scuncfromlocalpath.md)


[<span data-ttu-id="41061-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="41061-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="41061-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="41061-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="41061-140">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="41061-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="41061-141">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="41061-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

