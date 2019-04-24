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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 05df7fe04f511de9310edc7a8ef09130e6354ad2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327228"
---
# <a name="pidtagattachpathname-canonical-property"></a><span data-ttu-id="59fc6-103">PidTagAttachPathname 规范属性</span><span class="sxs-lookup"><span data-stu-id="59fc6-103">PidTagAttachPathname Canonical Property</span></span>

  
  
<span data-ttu-id="59fc6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59fc6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="59fc6-105">包含附件的完全限定的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="59fc6-105">Contains an attachment's fully-qualified path and filename.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="59fc6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="59fc6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="59fc6-107">PR_ATTACH_PATHNAME、PR_ATTACH_PATHNAME_A、PR_ATTACH_PATHNAME_W</span><span class="sxs-lookup"><span data-stu-id="59fc6-107">PR_ATTACH_PATHNAME, PR_ATTACH_PATHNAME_A, PR_ATTACH_PATHNAME_W</span></span>  <br/> |
|<span data-ttu-id="59fc6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="59fc6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="59fc6-109">0x3708</span><span class="sxs-lookup"><span data-stu-id="59fc6-109">0x3708</span></span>  <br/> |
|<span data-ttu-id="59fc6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="59fc6-110">Data type:</span></span>  <br/> |<span data-ttu-id="59fc6-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="59fc6-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="59fc6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="59fc6-112">Area:</span></span>  <br/> |<span data-ttu-id="59fc6-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="59fc6-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="59fc6-114">注解</span><span class="sxs-lookup"><span data-stu-id="59fc6-114">Remarks</span></span>

<span data-ttu-id="59fc6-115">建议附件子类型公开这些属性。</span><span class="sxs-lookup"><span data-stu-id="59fc6-115">It is recommended that attachment subobjects expose these properties.</span></span> <span data-ttu-id="59fc6-116">设置它们表示附件数据不包括在邮件中, 但在常见的文件服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="59fc6-116">Setting them indicates that the attachment data is not included with the message but is available on a common file server.</span></span> <span data-ttu-id="59fc6-117">这些属性与任何指示附件的**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 标志联合在一起都是必需的: **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**或**ATTACH_BY_REF_仅限**。</span><span class="sxs-lookup"><span data-stu-id="59fc6-117">These properties are required in conjunction with any of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) flags that indicate attachment by reference: **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, or **ATTACH_BY_REF_ONLY**.</span></span> 
  
<span data-ttu-id="59fc6-118">每个目录或文件名的限制为八个字符的名称加上三个字符的扩展名。</span><span class="sxs-lookup"><span data-stu-id="59fc6-118">Each directory or filename is restricted to an eight-character name plus a three-character extension.</span></span> <span data-ttu-id="59fc6-119">整个路径限制为256个字符。</span><span class="sxs-lookup"><span data-stu-id="59fc6-119">The overall path is restricted to 256 characters.</span></span> <span data-ttu-id="59fc6-120">对于支持长文件名的平台, 请同时设置这两个属性和**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="59fc6-120">For a platform that supports long filenames, set both these properties and **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)).</span></span> 
  
<span data-ttu-id="59fc6-121">在大多数情况下, 客户端应用程序应使用通用命名约定 (UNC), 在文件为本地文件时, 应使用绝对路径。</span><span class="sxs-lookup"><span data-stu-id="59fc6-121">Client applications should use a universal naming convention (UNC) in most cases when the file is shared, and should use an absolute path when the file is local.</span></span>
  
<span data-ttu-id="59fc6-122">MAPI 仅适用于 ANSI 字符集中的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="59fc6-122">MAPI works only with paths and filenames in the ANSI character set.</span></span> <span data-ttu-id="59fc6-123">在 OEM 字符集中使用路径和文件名的客户端必须先将其转换为 ANSI, 然后再调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="59fc6-123">Clients that use paths and filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="59fc6-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="59fc6-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="59fc6-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="59fc6-125">Protocol specifications</span></span>

<span data-ttu-id="59fc6-126">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59fc6-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59fc6-127">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="59fc6-127">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="59fc6-128">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="59fc6-128">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="59fc6-129">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="59fc6-129">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="59fc6-130">头文件</span><span class="sxs-lookup"><span data-stu-id="59fc6-130">Header files</span></span>

<span data-ttu-id="59fc6-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="59fc6-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="59fc6-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="59fc6-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="59fc6-133">Mapitags</span><span class="sxs-lookup"><span data-stu-id="59fc6-133">Mapitags.h</span></span>
  
> <span data-ttu-id="59fc6-134">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="59fc6-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="59fc6-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59fc6-135">See also</span></span>



[<span data-ttu-id="59fc6-136">ScLocalPathFromUNC</span><span class="sxs-lookup"><span data-stu-id="59fc6-136">ScLocalPathFromUNC</span></span>](sclocalpathfromunc.md)
  
[<span data-ttu-id="59fc6-137">ScUNCFromLocalPath</span><span class="sxs-lookup"><span data-stu-id="59fc6-137">ScUNCFromLocalPath</span></span>](scuncfromlocalpath.md)


[<span data-ttu-id="59fc6-138">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="59fc6-138">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="59fc6-139">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="59fc6-139">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="59fc6-140">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="59fc6-140">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="59fc6-141">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="59fc6-141">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

