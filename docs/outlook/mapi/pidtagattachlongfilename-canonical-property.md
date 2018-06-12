---
title: PidTagAttachLongFilename 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachLongFilename
api_type:
- HeaderDef
ms.assetid: 83b69e8f-0b5a-4992-b5b8-160d3bdfa22a
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0debee5d480c4ea0c0a8fb4b54d9fa5d92a45987
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777344"
---
# <a name="pidtagattachlongfilename-canonical-property"></a><span data-ttu-id="ec75c-103">PidTagAttachLongFilename 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec75c-103">PidTagAttachLongFilename Canonical Property</span></span>

  
  
<span data-ttu-id="ec75c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ec75c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ec75c-105">包含附件的长文件名和扩展名，不包括路径。</span><span class="sxs-lookup"><span data-stu-id="ec75c-105">Contains an attachment's long filename and extension, excluding path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ec75c-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="ec75c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ec75c-107">PR_ATTACH_LONG_FILENAME，PR_ATTACH_LONG_FILENAME_A，PR_ATTACH_LONG_FILENAME_W</span><span class="sxs-lookup"><span data-stu-id="ec75c-107">PR_ATTACH_LONG_FILENAME, PR_ATTACH_LONG_FILENAME_A, PR_ATTACH_LONG_FILENAME_W</span></span>  <br/> |
|<span data-ttu-id="ec75c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ec75c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ec75c-109">0x3707</span><span class="sxs-lookup"><span data-stu-id="ec75c-109">0x3707</span></span>  <br/> |
|<span data-ttu-id="ec75c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ec75c-110">Data type:</span></span>  <br/> |<span data-ttu-id="ec75c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ec75c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ec75c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ec75c-112">Area:</span></span>  <br/> |<span data-ttu-id="ec75c-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="ec75c-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ec75c-114">备注</span><span class="sxs-lookup"><span data-stu-id="ec75c-114">Remarks</span></span>

<span data-ttu-id="ec75c-115">这些属性与 ATTACH_BY_VALUE、 ATTACH_BY_REFERENCE、 ATTACH_BY_REF_RESOLVE 和 ATTACH_BY_REF_ONLY **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="ec75c-115">These properties pertain to the ATTACH_BY_VALUE, ATTACH_BY_REFERENCE, ATTACH_BY_REF_RESOLVE, and ATTACH_BY_REF_ONLY values of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span> <span data-ttu-id="ec75c-116">支持长文件名的平台应发送时，设置的**PR_ATTACH_LONG_FILENAME**和**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 属性，并应检查**PR_ATTACH_LONG_FILENAME**首先时接收。</span><span class="sxs-lookup"><span data-stu-id="ec75c-116">Platforms that support long filenames should set both the **PR_ATTACH_LONG_FILENAME** and **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) properties when sending, and should check **PR_ATTACH_LONG_FILENAME** first when receiving.</span></span> 
  
<span data-ttu-id="ec75c-117">客户端应用程序应将此属性设置为建议的长文件名用于接收邮件主机支持长文件名。</span><span class="sxs-lookup"><span data-stu-id="ec75c-117">The client application should set this property to a suggested long filename to be used if the host computer receiving a message supports long filenames.</span></span> <span data-ttu-id="ec75c-118">**PR_ATTACH_LONG_FILENAME**可以用作文件名，用于保存附件，并提供文件扩展名，如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ec75c-118">**PR_ATTACH_LONG_FILENAME** can be used as a filename for saving the attachment, and to supply the filename extension if the **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) property is not provided.</span></span> 
  
<span data-ttu-id="ec75c-119">与供稿**PR_ATTACH_FILENAME**文件名，此名称不是限制为八个字符 filename 扩展名为三个字符。</span><span class="sxs-lookup"><span data-stu-id="ec75c-119">Unlike the filename provided by **PR_ATTACH_FILENAME**, this name is not restricted to an eight-character filename plus a three-character extension.</span></span> <span data-ttu-id="ec75c-120">相反，它可以是最多 256 个字符长，包括文件名、 extension 和分隔符句号。</span><span class="sxs-lookup"><span data-stu-id="ec75c-120">Instead, it can be up to 256 characters long, including the filename, extension, and separator period.</span></span> 
  
<span data-ttu-id="ec75c-121">MAPI 仅适用于 ANSI 字符集中的文件名。</span><span class="sxs-lookup"><span data-stu-id="ec75c-121">MAPI works only with filenames in the ANSI character set.</span></span> <span data-ttu-id="ec75c-122">使用 OEM 字符集中的文件名的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="ec75c-122">Client applications that use filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ec75c-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="ec75c-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ec75c-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="ec75c-124">Protocol specifications</span></span>

<span data-ttu-id="ec75c-125">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec75c-125">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec75c-126">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="ec75c-126">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ec75c-127">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec75c-127">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec75c-128">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="ec75c-128">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="ec75c-129">[[MS OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec75c-129">[[MS-OXORMMS]](http://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec75c-130">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="ec75c-130">Specifies the properties of rights-managed encoded messages.</span></span>
    
<span data-ttu-id="ec75c-131">[[MS OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ec75c-131">[[MS-OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ec75c-132">指定的属性和操作所允许的表示语音邮件和传真消息。</span><span class="sxs-lookup"><span data-stu-id="ec75c-132">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ec75c-133">头文件</span><span class="sxs-lookup"><span data-stu-id="ec75c-133">Header files</span></span>

<span data-ttu-id="ec75c-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ec75c-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="ec75c-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ec75c-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="ec75c-136">Mmapitags.h</span><span class="sxs-lookup"><span data-stu-id="ec75c-136">Mmapitags.h</span></span>
  
> <span data-ttu-id="ec75c-137">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ec75c-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ec75c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec75c-138">See also</span></span>



[<span data-ttu-id="ec75c-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ec75c-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ec75c-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ec75c-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ec75c-141">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec75c-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ec75c-142">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ec75c-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

