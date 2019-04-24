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
# <a name="pidtagattachlongfilename-canonical-property"></a><span data-ttu-id="03f1f-103">PidTagAttachLongFilename 规范属性</span><span class="sxs-lookup"><span data-stu-id="03f1f-103">PidTagAttachLongFilename Canonical Property</span></span>

  
  
<span data-ttu-id="03f1f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="03f1f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="03f1f-105">包含附件的长文件名和扩展名 (不包括路径)。</span><span class="sxs-lookup"><span data-stu-id="03f1f-105">Contains an attachment's long filename and extension, excluding path.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="03f1f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="03f1f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="03f1f-107">PR_ATTACH_LONG_FILENAME、PR_ATTACH_LONG_FILENAME_A、PR_ATTACH_LONG_FILENAME_W</span><span class="sxs-lookup"><span data-stu-id="03f1f-107">PR_ATTACH_LONG_FILENAME, PR_ATTACH_LONG_FILENAME_A, PR_ATTACH_LONG_FILENAME_W</span></span>  <br/> |
|<span data-ttu-id="03f1f-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="03f1f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="03f1f-109">0x3707</span><span class="sxs-lookup"><span data-stu-id="03f1f-109">0x3707</span></span>  <br/> |
|<span data-ttu-id="03f1f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="03f1f-110">Data type:</span></span>  <br/> |<span data-ttu-id="03f1f-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="03f1f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="03f1f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="03f1f-112">Area:</span></span>  <br/> |<span data-ttu-id="03f1f-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="03f1f-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="03f1f-114">注解</span><span class="sxs-lookup"><span data-stu-id="03f1f-114">Remarks</span></span>

<span data-ttu-id="03f1f-115">这些属性与**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性的 ATTACH_BY_VALUE、ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE 和 ATTACH_BY_REF_ONLY 值相关。</span><span class="sxs-lookup"><span data-stu-id="03f1f-115">These properties pertain to the ATTACH_BY_VALUE, ATTACH_BY_REFERENCE, ATTACH_BY_REF_RESOLVE, and ATTACH_BY_REF_ONLY values of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span> <span data-ttu-id="03f1f-116">支持长文件名的平台应在发送时同时设置**PR_ATTACH_LONG_FILENAME**和**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 属性, 并应先检查**PR_ATTACH_LONG_FILENAME**收货.</span><span class="sxs-lookup"><span data-stu-id="03f1f-116">Platforms that support long filenames should set both the **PR_ATTACH_LONG_FILENAME** and **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) properties when sending, and should check **PR_ATTACH_LONG_FILENAME** first when receiving.</span></span> 
  
<span data-ttu-id="03f1f-117">如果接收邮件的主机计算机支持长文件名, 客户端应用程序应将此属性设置为建议使用的长文件名。</span><span class="sxs-lookup"><span data-stu-id="03f1f-117">The client application should set this property to a suggested long filename to be used if the host computer receiving a message supports long filenames.</span></span> <span data-ttu-id="03f1f-118">**PR_ATTACH_LONG_FILENAME**可用作保存附件的文件名, 如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性, 则提供文件名扩展。</span><span class="sxs-lookup"><span data-stu-id="03f1f-118">**PR_ATTACH_LONG_FILENAME** can be used as a filename for saving the attachment, and to supply the filename extension if the **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) property is not provided.</span></span> 
  
<span data-ttu-id="03f1f-119">与**PR_ATTACH_FILENAME**提供的文件名不同, 此名称不限制为8个字符的文件名加上三个字符的扩展名。</span><span class="sxs-lookup"><span data-stu-id="03f1f-119">Unlike the filename provided by **PR_ATTACH_FILENAME**, this name is not restricted to an eight-character filename plus a three-character extension.</span></span> <span data-ttu-id="03f1f-120">相反, 它的最大长度为256个字符, 包括文件名、扩展名和分隔符期。</span><span class="sxs-lookup"><span data-stu-id="03f1f-120">Instead, it can be up to 256 characters long, including the filename, extension, and separator period.</span></span> 
  
<span data-ttu-id="03f1f-121">MAPI 仅适用于 ANSI 字符集中的文件名。</span><span class="sxs-lookup"><span data-stu-id="03f1f-121">MAPI works only with filenames in the ANSI character set.</span></span> <span data-ttu-id="03f1f-122">使用 OEM 字符集中的文件名的客户端应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="03f1f-122">Client applications that use filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="03f1f-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="03f1f-123">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="03f1f-124">协议规范</span><span class="sxs-lookup"><span data-stu-id="03f1f-124">Protocol specifications</span></span>

<span data-ttu-id="03f1f-125">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03f1f-125">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03f1f-126">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="03f1f-126">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="03f1f-127">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03f1f-127">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03f1f-128">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="03f1f-128">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="03f1f-129">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03f1f-129">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03f1f-130">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="03f1f-130">Specifies the properties of rights-managed encoded messages.</span></span>
    
<span data-ttu-id="03f1f-131">[[毫秒-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="03f1f-131">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="03f1f-132">指定允许表示语音邮件和传真邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="03f1f-132">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="03f1f-133">头文件</span><span class="sxs-lookup"><span data-stu-id="03f1f-133">Header files</span></span>

<span data-ttu-id="03f1f-134">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="03f1f-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="03f1f-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="03f1f-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="03f1f-136">Mmapitags</span><span class="sxs-lookup"><span data-stu-id="03f1f-136">Mmapitags.h</span></span>
  
> <span data-ttu-id="03f1f-137">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="03f1f-137">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03f1f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03f1f-138">See also</span></span>



[<span data-ttu-id="03f1f-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="03f1f-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="03f1f-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="03f1f-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="03f1f-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="03f1f-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="03f1f-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="03f1f-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

