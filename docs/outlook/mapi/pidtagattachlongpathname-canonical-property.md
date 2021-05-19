---
title: PidTagAttachLongPathname 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachLongPathname
api_type:
- HeaderDef
ms.assetid: 3262cf95-48b5-4764-a96e-d752ce35b2dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d8fe8525cf4fc11ac17ed6d73fb5d97e4f2d003e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339366"
---
# <a name="pidtagattachlongpathname-canonical-property"></a><span data-ttu-id="0e4b2-103">PidTagAttachLongPathname 规范属性</span><span class="sxs-lookup"><span data-stu-id="0e4b2-103">PidTagAttachLongPathname Canonical Property</span></span>

  
  
<span data-ttu-id="0e4b2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e4b2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0e4b2-105">包含附件的完全限定长路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-105">Contains an attachment's fully-qualified long path and filename.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0e4b2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0e4b2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0e4b2-107">PR_ATTACH_LONG_PATHNAME、PR_ATTACH_LONG_PATHNAME_A、PR_ATTACH_LONG_PATHNAME_W</span><span class="sxs-lookup"><span data-stu-id="0e4b2-107">PR_ATTACH_LONG_PATHNAME, PR_ATTACH_LONG_PATHNAME_A, PR_ATTACH_LONG_PATHNAME_W</span></span>  <br/> |
|<span data-ttu-id="0e4b2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0e4b2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0e4b2-109">0x370D</span><span class="sxs-lookup"><span data-stu-id="0e4b2-109">0x370D</span></span>  <br/> |
|<span data-ttu-id="0e4b2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0e4b2-110">Data type:</span></span>  <br/> |<span data-ttu-id="0e4b2-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0e4b2-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0e4b2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0e4b2-112">Area:</span></span>  <br/> |<span data-ttu-id="0e4b2-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="0e4b2-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0e4b2-114">备注</span><span class="sxs-lookup"><span data-stu-id="0e4b2-114">Remarks</span></span>

<span data-ttu-id="0e4b2-115">这些属性适用于使用通过引用指示附件的任何 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性值 **：ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE** 或 **ATTACH_BY_REF_ONLY**。 </span><span class="sxs-lookup"><span data-stu-id="0e4b2-115">These properties are applicable when you use any of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property's values that indicate attachment by reference: **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, or **ATTACH_BY_REF_ONLY**.</span></span> <span data-ttu-id="0e4b2-116">支持长文件名的平台应在发送时同时设置 **PR_ATTACH_LONG_PATHNAME** 或关联属性和 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 属性，并且应在接收时先检查 **PR_ATTACH_LONG_PATHNAME** 或关联属性。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-116">Platforms that support long filenames should set both **PR_ATTACH_LONG_PATHNAME** or associated properties and **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) properties when sending, and should check **PR_ATTACH_LONG_PATHNAME** or associated properties first when receiving.</span></span> 
  
<span data-ttu-id="0e4b2-117">如果接收邮件的主机支持长文件名，客户端应用程序应将这些属性设置为建议的长路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-117">The client application should set these properties to a suggested long path and filename to be used if the host machine receiving a message supports long filenames.</span></span> <span data-ttu-id="0e4b2-118">设置这些属性表示附件数据不包含在邮件中，但在公用文件服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-118">Setting these properties indicates that the attachment data is not included with the message but is available on a common file server.</span></span> 
  
<span data-ttu-id="0e4b2-119">与 PR_ATTACH_PATHNAME 提供的目录和文件名不同，这些目录和文件名不限于八字符目录或文件名加三字符扩展名。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-119">Unlike the directories and filenames provided by **PR_ATTACH_PATHNAME**, these directories and filenames are not restricted to an eight-character directory or filename plus three-character extension.</span></span> <span data-ttu-id="0e4b2-120">相反，每个目录或文件名最多为 256 个字符，包括名称、扩展名和分隔符。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-120">Instead, each directory or filename can be up to 256 characters long, including the name, extension, and separator period.</span></span> <span data-ttu-id="0e4b2-121">但是，整个路径限制为 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-121">However, the overall path is limited to 256 characters.</span></span> 
  
<span data-ttu-id="0e4b2-122">客户端应在共享文件时 (UNC) 通用命名约定，并且应在文件是本地文件时使用绝对路径。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-122">Clients should use a universal naming convention (UNC) in most cases when the file is shared, and should use an absolute path when the file is local.</span></span>
  
<span data-ttu-id="0e4b2-123">MAPI 仅适用于 ANSI 字符集内的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-123">MAPI works only with paths and filenames in the ANSI character set.</span></span> <span data-ttu-id="0e4b2-124">在 OEM 字符集内使用路径和文件名的客户端应用程序必须先将其转换为 ANSI，然后才能调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-124">Client applications that use paths and filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0e4b2-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="0e4b2-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0e4b2-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="0e4b2-126">Protocol specifications</span></span>

<span data-ttu-id="0e4b2-127">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4b2-127">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0e4b2-128">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-128">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="0e4b2-129">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e4b2-129">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0e4b2-130">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-130">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0e4b2-131">头文件</span><span class="sxs-lookup"><span data-stu-id="0e4b2-131">Header files</span></span>

<span data-ttu-id="0e4b2-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0e4b2-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="0e4b2-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="0e4b2-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0e4b2-134">Mapitags.h</span></span>
  
> <span data-ttu-id="0e4b2-135">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0e4b2-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0e4b2-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e4b2-136">See also</span></span>



[<span data-ttu-id="0e4b2-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0e4b2-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0e4b2-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0e4b2-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0e4b2-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0e4b2-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0e4b2-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0e4b2-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

