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
ms.openlocfilehash: c0a3a96c3d8835550c4b0fda233183214cb4a786
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587423"
---
# <a name="pidtagattachlongpathname-canonical-property"></a><span data-ttu-id="87a4c-103">PidTagAttachLongPathname 规范属性</span><span class="sxs-lookup"><span data-stu-id="87a4c-103">PidTagAttachLongPathname Canonical Property</span></span>

  
  
<span data-ttu-id="87a4c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="87a4c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="87a4c-105">包含附件的完全限定长路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="87a4c-105">Contains an attachment's fully-qualified long path and filename.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="87a4c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="87a4c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="87a4c-107">PR_ATTACH_LONG_PATHNAME，PR_ATTACH_LONG_PATHNAME_A，PR_ATTACH_LONG_PATHNAME_W</span><span class="sxs-lookup"><span data-stu-id="87a4c-107">PR_ATTACH_LONG_PATHNAME, PR_ATTACH_LONG_PATHNAME_A, PR_ATTACH_LONG_PATHNAME_W</span></span>  <br/> |
|<span data-ttu-id="87a4c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="87a4c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="87a4c-109">0x370D</span><span class="sxs-lookup"><span data-stu-id="87a4c-109">0x370D</span></span>  <br/> |
|<span data-ttu-id="87a4c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="87a4c-110">Data type:</span></span>  <br/> |<span data-ttu-id="87a4c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="87a4c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="87a4c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="87a4c-112">Area:</span></span>  <br/> |<span data-ttu-id="87a4c-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="87a4c-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="87a4c-114">注解</span><span class="sxs-lookup"><span data-stu-id="87a4c-114">Remarks</span></span>

<span data-ttu-id="87a4c-115">您可以使用任何指示附件通过引用**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值时，这些属性都适用： **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**或**ATTACH_BY_REF_ONLY**。</span><span class="sxs-lookup"><span data-stu-id="87a4c-115">These properties are applicable when you use any of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property's values that indicate attachment by reference: **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, or **ATTACH_BY_REF_ONLY**.</span></span> <span data-ttu-id="87a4c-116">支持长文件名的平台应设置**PR_ATTACH_LONG_PATHNAME**或相关的属性和时发送，并应检查**PR_ATTACH_LONG_PATHNAME **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 属性**或时接收首先关联的属性。</span><span class="sxs-lookup"><span data-stu-id="87a4c-116">Platforms that support long filenames should set both **PR_ATTACH_LONG_PATHNAME** or associated properties and **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) properties when sending, and should check **PR_ATTACH_LONG_PATHNAME** or associated properties first when receiving.</span></span> 
  
<span data-ttu-id="87a4c-117">客户端应用程序应将这些属性设置为建议长路径和文件名用于接收邮件主机支持长文件名。</span><span class="sxs-lookup"><span data-stu-id="87a4c-117">The client application should set these properties to a suggested long path and filename to be used if the host machine receiving a message supports long filenames.</span></span> <span data-ttu-id="87a4c-118">设置这些属性指示附件数据不包含在邮件，但在常见的文件服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="87a4c-118">Setting these properties indicates that the attachment data is not included with the message but is available on a common file server.</span></span> 
  
<span data-ttu-id="87a4c-119">与不同的目录和供稿**PR_ATTACH_PATHNAME**的文件名，这些目录和文件名不限制为八个字符目录或文件名扩展名三个字符。</span><span class="sxs-lookup"><span data-stu-id="87a4c-119">Unlike the directories and filenames provided by **PR_ATTACH_PATHNAME**, these directories and filenames are not restricted to an eight-character directory or filename plus three-character extension.</span></span> <span data-ttu-id="87a4c-120">而是每个目录或文件名可以最多 256 个字符长，包括名称、 extension 和分隔符时间段。</span><span class="sxs-lookup"><span data-stu-id="87a4c-120">Instead, each directory or filename can be up to 256 characters long, including the name, extension, and separator period.</span></span> <span data-ttu-id="87a4c-121">但是，总体路径仅限于 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="87a4c-121">However, the overall path is limited to 256 characters.</span></span> 
  
<span data-ttu-id="87a4c-122">文件共享，以及本地文件时，应使用绝对路径时，客户端应在大多数情况下使用通用命名约定 (UNC)。</span><span class="sxs-lookup"><span data-stu-id="87a4c-122">Clients should use a universal naming convention (UNC) in most cases when the file is shared, and should use an absolute path when the file is local.</span></span>
  
<span data-ttu-id="87a4c-123">MAPI 仅适用于路径和文件名 ansi 字符集。</span><span class="sxs-lookup"><span data-stu-id="87a4c-123">MAPI works only with paths and filenames in the ANSI character set.</span></span> <span data-ttu-id="87a4c-124">使用 OEM 字符集中的路径和文件名的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="87a4c-124">Client applications that use paths and filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="87a4c-125">相关资源</span><span class="sxs-lookup"><span data-stu-id="87a4c-125">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="87a4c-126">协议规范</span><span class="sxs-lookup"><span data-stu-id="87a4c-126">Protocol specifications</span></span>

<span data-ttu-id="87a4c-127">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87a4c-127">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87a4c-128">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="87a4c-128">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="87a4c-129">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="87a4c-129">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="87a4c-130">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="87a4c-130">Specifies the properties of rights-managed encoded messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="87a4c-131">头文件</span><span class="sxs-lookup"><span data-stu-id="87a4c-131">Header files</span></span>

<span data-ttu-id="87a4c-132">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="87a4c-132">Mapidefs.h</span></span>
  
> <span data-ttu-id="87a4c-133">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="87a4c-133">Provides data type definitions.</span></span>
    
<span data-ttu-id="87a4c-134">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="87a4c-134">Mapitags.h</span></span>
  
> <span data-ttu-id="87a4c-135">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="87a4c-135">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="87a4c-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87a4c-136">See also</span></span>



[<span data-ttu-id="87a4c-137">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="87a4c-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="87a4c-138">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="87a4c-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="87a4c-139">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="87a4c-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="87a4c-140">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="87a4c-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

