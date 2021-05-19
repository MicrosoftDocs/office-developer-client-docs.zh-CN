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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45b6b3fb0c67d854fddf3773c06cef7b36f54992
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339324"
---
# <a name="pidtagattachlongfilename-canonical-property"></a><span data-ttu-id="a9c04-103">PidTagAttachLongFilename 规范属性</span><span class="sxs-lookup"><span data-stu-id="a9c04-103">PidTagAttachLongFilename Canonical Property</span></span>

  
  
<span data-ttu-id="a9c04-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9c04-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9c04-105">包含附件的长文件名和扩展名，不包括路径。</span><span class="sxs-lookup"><span data-stu-id="a9c04-105">Contains an attachment's long filename and extension, excluding path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a9c04-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a9c04-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a9c04-107">PR_ATTACH_LONG_FILENAME、PR_ATTACH_LONG_FILENAME_A、PR_ATTACH_LONG_FILENAME_W</span><span class="sxs-lookup"><span data-stu-id="a9c04-107">PR_ATTACH_LONG_FILENAME, PR_ATTACH_LONG_FILENAME_A, PR_ATTACH_LONG_FILENAME_W</span></span>  <br/> |
|<span data-ttu-id="a9c04-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="a9c04-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a9c04-109">0x3707</span><span class="sxs-lookup"><span data-stu-id="a9c04-109">0x3707</span></span>  <br/> |
|<span data-ttu-id="a9c04-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a9c04-110">Data type:</span></span>  <br/> |<span data-ttu-id="a9c04-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a9c04-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="a9c04-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a9c04-112">Area:</span></span>  <br/> |<span data-ttu-id="a9c04-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="a9c04-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a9c04-114">备注</span><span class="sxs-lookup"><span data-stu-id="a9c04-114">Remarks</span></span>

<span data-ttu-id="a9c04-115">这些属性与 ATTACH_BY_VALUE [PidTagAttachMethod](pidtagattachmethod-canonical-property.md) PR_ATTACH_METHOD ATTACH_BY_REFERENCE ATTACH_BY_REF_RESOLVE ATTACH_BY_REF_ONLY 属性的 PR_ATTACH_METHOD  (、ATTACH_BY_REF_RESOLVE 和) 值相关。</span><span class="sxs-lookup"><span data-stu-id="a9c04-115">These properties pertain to the ATTACH_BY_VALUE, ATTACH_BY_REFERENCE, ATTACH_BY_REF_RESOLVE, and ATTACH_BY_REF_ONLY values of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span> <span data-ttu-id="a9c04-116">在发送时，支持长文件名的平台应同时设置 **PR_ATTACH_LONG_FILENAME** 和 **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 属性，并且应在接收时PR_ATTACH_LONG_FILENAME检查文件。 </span><span class="sxs-lookup"><span data-stu-id="a9c04-116">Platforms that support long filenames should set both the **PR_ATTACH_LONG_FILENAME** and **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) properties when sending, and should check **PR_ATTACH_LONG_FILENAME** first when receiving.</span></span> 
  
<span data-ttu-id="a9c04-117">如果接收邮件的主机支持长文件名，客户端应用程序应将此属性设置为建议使用的长文件名。</span><span class="sxs-lookup"><span data-stu-id="a9c04-117">The client application should set this property to a suggested long filename to be used if the host computer receiving a message supports long filenames.</span></span> <span data-ttu-id="a9c04-118">**PR_ATTACH_LONG_FILENAME** 用作保存附件的文件名，如果未提供 **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) ，则提供文件名扩展名。</span><span class="sxs-lookup"><span data-stu-id="a9c04-118">**PR_ATTACH_LONG_FILENAME** can be used as a filename for saving the attachment, and to supply the filename extension if the **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) property is not provided.</span></span> 
  
<span data-ttu-id="a9c04-119">与由 PR_ATTACH_FILENAME 提供的文件名不同，此名称不限于八字符文件名和三字符扩展名。</span><span class="sxs-lookup"><span data-stu-id="a9c04-119">Unlike the filename provided by **PR_ATTACH_FILENAME**, this name is not restricted to an eight-character filename plus a three-character extension.</span></span> <span data-ttu-id="a9c04-120">相反，它可以最多为 256 个字符，包括文件名、扩展名和分隔符段。</span><span class="sxs-lookup"><span data-stu-id="a9c04-120">Instead, it can be up to 256 characters long, including the filename, extension, and separator period.</span></span> 
  
<span data-ttu-id="a9c04-121">MAPI 仅适用于 ANSI 字符集的文件名。</span><span class="sxs-lookup"><span data-stu-id="a9c04-121">MAPI works only with filenames in the ANSI character set.</span></span> <span data-ttu-id="a9c04-122">在 OEM 字符集内使用文件名的客户端应用程序必须先将其转换为 ANSI，然后才能调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="a9c04-122">Client applications that use filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="a9c04-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="a9c04-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a9c04-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="a9c04-124">Protocol specifications</span></span>

<span data-ttu-id="a9c04-125">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9c04-125">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a9c04-126">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="a9c04-126">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="a9c04-127">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9c04-127">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a9c04-128">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="a9c04-128">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="a9c04-129">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9c04-129">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a9c04-130">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="a9c04-130">Specifies the properties of rights-managed encoded messages.</span></span>
    
<span data-ttu-id="a9c04-131">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a9c04-131">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a9c04-132">指定允许用于表示语音邮件和传真邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="a9c04-132">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a9c04-133">头文件</span><span class="sxs-lookup"><span data-stu-id="a9c04-133">Header files</span></span>

<span data-ttu-id="a9c04-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a9c04-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="a9c04-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a9c04-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="a9c04-136">Mmapitags.h</span><span class="sxs-lookup"><span data-stu-id="a9c04-136">Mmapitags.h</span></span>
  
> <span data-ttu-id="a9c04-137">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a9c04-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a9c04-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9c04-138">See also</span></span>



[<span data-ttu-id="a9c04-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a9c04-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a9c04-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a9c04-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a9c04-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a9c04-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a9c04-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a9c04-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

