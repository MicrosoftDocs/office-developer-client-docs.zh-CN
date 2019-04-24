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
ms.openlocfilehash: f5dcf90e8224f1bf2e96042a7344109293cc2c3f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319220"
---
# <a name="pidtagattachfilename-canonical-property"></a><span data-ttu-id="ef2d6-103">PidTagAttachFilename 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef2d6-103">PidTagAttachFilename Canonical Property</span></span>

  
  
<span data-ttu-id="ef2d6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ef2d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ef2d6-105">包含附件的基文件名和扩展名 (不包括路径)。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-105">Contains an attachment's base file name and extension, excluding path.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef2d6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ef2d6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ef2d6-107">PR_ATTACH_FILENAME、PR_ATTACH_FILENAME_A、PR_ATTACH_FILENAME_W</span><span class="sxs-lookup"><span data-stu-id="ef2d6-107">PR_ATTACH_FILENAME, PR_ATTACH_FILENAME_A, PR_ATTACH_FILENAME_W</span></span>  <br/> |
|<span data-ttu-id="ef2d6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ef2d6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ef2d6-109">0x3704</span><span class="sxs-lookup"><span data-stu-id="ef2d6-109">0x3704</span></span>  <br/> |
|<span data-ttu-id="ef2d6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ef2d6-110">Data type:</span></span>  <br/> |<span data-ttu-id="ef2d6-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ef2d6-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ef2d6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ef2d6-112">Area:</span></span>  <br/> |<span data-ttu-id="ef2d6-113">邮件附件</span><span class="sxs-lookup"><span data-stu-id="ef2d6-113">Message attachment</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ef2d6-114">注解</span><span class="sxs-lookup"><span data-stu-id="ef2d6-114">Remarks</span></span>

<span data-ttu-id="ef2d6-115">建议附件对象公开这些属性, 这些属性与**PR_ATTACH_METHOD**的**ATTACH_BY_VALUE**、 **ATTACH_BY_REFERENCE**、 **ATTACH_BY_REF_RESOLVE**和**ATTACH_BY_REF_ONLY**值相关。([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-115">It is recommended that attachment objects expose these properties which pertain to the **ATTACH_BY_VALUE**, **ATTACH_BY_REFERENCE**, **ATTACH_BY_REF_RESOLVE**, and **ATTACH_BY_REF_ONLY** values of the **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) property.</span></span> <span data-ttu-id="ef2d6-116">使用这些值中的任何一个时, **PR_ATTACH_FILENAME**和关联属性都是必需的。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-116">**PR_ATTACH_FILENAME** and associated properties are required when any of these values is used.</span></span> 
  
<span data-ttu-id="ef2d6-117">这些属性可用作保存附件的建议文件名, 如果未提供**PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) 属性, 则提供文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-117">These properties can be used as a suggested file name for saving the attachment and to supply the file name extension if the **PR_ATTACH_EXTENSION** ([PidTagAttachExtension](pidtagattachextension-canonical-property.md)) property is not provided.</span></span> 
  
<span data-ttu-id="ef2d6-118">文件名限制为八个字符加上三个字符的扩展名。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-118">The file name is restricted to eight characters plus a three-character extension.</span></span> <span data-ttu-id="ef2d6-119">对于支持长文件名的平台, 请同时设置此属性和**PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-119">For a platform that supports long file names, set both this property and the **PR_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="ef2d6-120">MAPI 仅适用于文件名以及传递给它的其他字符串 (美国国家标准协会 (ANSI) 字符集)。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-120">MAPI works only with file names, and other strings passed to it, in the American National Standards Institute (ANSI) character set.</span></span> <span data-ttu-id="ef2d6-121">使用原始设备制造商 (OEM) 字符集中的文件名称的客户端应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-121">Client applications that use file names in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ef2d6-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="ef2d6-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ef2d6-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="ef2d6-123">Protocol specifications</span></span>

<span data-ttu-id="ef2d6-124">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef2d6-124">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef2d6-125">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-125">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ef2d6-126">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef2d6-126">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef2d6-127">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-127">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="ef2d6-128">[[毫秒-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef2d6-128">[[MS-OXORMMS]](https://msdn.microsoft.com/library/a121dda4-48f3-41f8-b12f-170f533038bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef2d6-129">指定权限管理编码邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-129">Specifies the properties of rights-managed encoded messages.</span></span>
    
<span data-ttu-id="ef2d6-130">[[毫秒-OXOSMIME]](https://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef2d6-130">[[MS-OXOSMIME]](https://msdn.microsoft.com/library/bb17d126-d211-462c-8cd3-454ed33c8746%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef2d6-131">指定 S/MIME 签名和加密的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-131">Specifies S/MIME signed and encrypted message properties.</span></span>
    
<span data-ttu-id="ef2d6-132">[[毫秒-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef2d6-132">[[MS-OXTNEF]](https://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef2d6-133">将邮件和附件对象编码并解码为高效流表示形式。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-133">Encodes and decodes message and attachment objects to an efficient stream representation.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ef2d6-134">头文件</span><span class="sxs-lookup"><span data-stu-id="ef2d6-134">Header files</span></span>

<span data-ttu-id="ef2d6-135">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ef2d6-135">Mapidefs.h</span></span>
  
> <span data-ttu-id="ef2d6-136">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-136">Provides data type definitions.</span></span>
    
<span data-ttu-id="ef2d6-137">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ef2d6-137">Mapitags.h</span></span>
  
> <span data-ttu-id="ef2d6-138">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ef2d6-138">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ef2d6-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef2d6-139">See also</span></span>



[<span data-ttu-id="ef2d6-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ef2d6-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ef2d6-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef2d6-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ef2d6-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ef2d6-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ef2d6-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ef2d6-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

