---
title: PidTagRtfCompressed 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfCompressed
api_type:
- COM
ms.assetid: fd0ccb88-55ce-4d7c-9573-6e5d6239b6a8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3091a76a1b755bf5a0d641ed9bd79bcfaa4641b7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357888"
---
# <a name="pidtagrtfcompressed-canonical-property"></a><span data-ttu-id="1b51d-103">PidTagRtfCompressed 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b51d-103">PidTagRtfCompressed Canonical Property</span></span>

  
  
<span data-ttu-id="1b51d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b51d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b51d-105">包含邮件文本的 rtf 格式 (rtf) 版本 (通常为压缩格式)。</span><span class="sxs-lookup"><span data-stu-id="1b51d-105">Contains the Rich Text Format (RTF) version of the message text, usually in compressed form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1b51d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1b51d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1b51d-107">PR_RTF_COMPRESSED</span><span class="sxs-lookup"><span data-stu-id="1b51d-107">PR_RTF_COMPRESSED</span></span>  <br/> |
|<span data-ttu-id="1b51d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="1b51d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1b51d-109">0x1009</span><span class="sxs-lookup"><span data-stu-id="1b51d-109">0x1009</span></span>  <br/> |
|<span data-ttu-id="1b51d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1b51d-110">Data type:</span></span>  <br/> |<span data-ttu-id="1b51d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="1b51d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="1b51d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1b51d-112">Area:</span></span>  <br/> |<span data-ttu-id="1b51d-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="1b51d-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1b51d-114">注解</span><span class="sxs-lookup"><span data-stu-id="1b51d-114">Remarks</span></span>

<span data-ttu-id="1b51d-115">此属性包含的邮件文本与**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性相同, 但格式为 RTF。</span><span class="sxs-lookup"><span data-stu-id="1b51d-115">This property contains the same message text as the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property but in RTF.</span></span> 
  
<span data-ttu-id="1b51d-116">RTF 中的邮件文本通常以压缩形式存储。</span><span class="sxs-lookup"><span data-stu-id="1b51d-116">Message text in RTF is normally stored in compressed form.</span></span> <span data-ttu-id="1b51d-117">但是, 有些系统不会压缩格式化文本。</span><span class="sxs-lookup"><span data-stu-id="1b51d-117">However, some systems do not compress formatted text.</span></span> <span data-ttu-id="1b51d-118">为了适应它们, MAPI 提供了流头的 dwMagicUncompressedRTF 值, 以标识未压缩的 RTF 以及邮件的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的**STORE_UNCOMPRESSED_RTF**标志store 以指示它可以存储解压缩的 RTF。</span><span class="sxs-lookup"><span data-stu-id="1b51d-118">To accommodate them, MAPI provides the dwMagicUncompressedRTF value for a stream header to identify uncompressed RTF, and the **STORE_UNCOMPRESSED_RTF** flag in **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) for the message store to indicate it can store uncompressed RTF.</span></span> 
  
<span data-ttu-id="1b51d-119">若要获取此属性的内容, 请调用**OpenProperty**, 然后使用**MAPI_READ**标志调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md) 。</span><span class="sxs-lookup"><span data-stu-id="1b51d-119">To obtain the contents of this property, call **OpenProperty**, then call [WrapCompressedRTFStream](wrapcompressedrtfstream.md) with the **MAPI_READ** flag.</span></span> <span data-ttu-id="1b51d-120">若要写入此属性, 请使用**MAPI_MODIFY**和**MAPI_CREATE**标志打开它。</span><span class="sxs-lookup"><span data-stu-id="1b51d-120">To write into this property, open it with the **MAPI_MODIFY** and **MAPI_CREATE** flags.</span></span> <span data-ttu-id="1b51d-121">这可确保新数据完全替换所有旧数据, 并使用最小存储更新数执行写入操作。</span><span class="sxs-lookup"><span data-stu-id="1b51d-121">This ensures that the new data completely replace any old data and that the writes are performed using the minimum number of store updates.</span></span> 
  
<span data-ttu-id="1b51d-122">支持 RTF 的邮件存储将忽略对邮件文本中的空格所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1b51d-122">Message stores that support RTF ignore any changes to white space in the message text.</span></span> <span data-ttu-id="1b51d-123">首次存储**PR_BODY**时, 邮件存储也会生成和存储此属性。</span><span class="sxs-lookup"><span data-stu-id="1b51d-123">When **PR_BODY** is stored for the first time, the message store also generates and stores this property.</span></span> <span data-ttu-id="1b51d-124">如果随后调用了[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法并修改了**PR_BODY** , 则邮件存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。</span><span class="sxs-lookup"><span data-stu-id="1b51d-124">If the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is subsequently called and **PR_BODY** has been modified, the message store calls the [RTFSync](rtfsync.md) function to ensure synchronization with the RTF version.</span></span> <span data-ttu-id="1b51d-125">如果只更改了空白, 则属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="1b51d-125">If only white space has been changed, the properties are left unchanged.</span></span> <span data-ttu-id="1b51d-126">当邮件通过非 RTF 感知客户端和邮件系统传输时, 这将保留任何 nontrivial RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="1b51d-126">This preserves any nontrivial RTF formatting when the message travels through non-RTF-aware clients and messaging systems.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="1b51d-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="1b51d-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1b51d-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="1b51d-128">Protocol specifications</span></span>

<span data-ttu-id="1b51d-129">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b51d-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b51d-130">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="1b51d-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1b51d-131">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b51d-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b51d-132">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="1b51d-132">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="1b51d-133">[[毫秒-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b51d-133">[[MS-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b51d-134">对 RTF 邮件正文中的压缩流进行编码和解码。</span><span class="sxs-lookup"><span data-stu-id="1b51d-134">Encodes and decodes a compressed stream in RTF message bodies.</span></span>
    
<span data-ttu-id="1b51d-135">[[毫秒-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1b51d-135">[[MS-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1b51d-136">封装邮件和附件的 RTF 正文属性中的其他内容格式 (如 HTML)。</span><span class="sxs-lookup"><span data-stu-id="1b51d-136">Encapsulates additional content formats (such as HTML) within the RTF body property of messages and attachments.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1b51d-137">头文件</span><span class="sxs-lookup"><span data-stu-id="1b51d-137">Header files</span></span>

<span data-ttu-id="1b51d-138">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1b51d-138">Mapidefs.h</span></span>
  
> <span data-ttu-id="1b51d-139">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1b51d-139">Provides data type definitions.</span></span>
    
<span data-ttu-id="1b51d-140">Mapitags</span><span class="sxs-lookup"><span data-stu-id="1b51d-140">Mapitags.h</span></span>
  
> <span data-ttu-id="1b51d-141">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1b51d-141">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1b51d-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b51d-142">See also</span></span>



[<span data-ttu-id="1b51d-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1b51d-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1b51d-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b51d-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1b51d-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1b51d-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1b51d-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1b51d-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

