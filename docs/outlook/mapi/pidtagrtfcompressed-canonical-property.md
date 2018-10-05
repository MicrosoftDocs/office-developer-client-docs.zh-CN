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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394889"
---
# <a name="pidtagrtfcompressed-canonical-property"></a><span data-ttu-id="b1287-103">PidTagRtfCompressed 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1287-103">PidTagRtfCompressed Canonical Property</span></span>

  
  
<span data-ttu-id="b1287-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1287-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1287-105">包含消息文本，通常在压缩的窗体中的富文本格式 (RTF) 版本。</span><span class="sxs-lookup"><span data-stu-id="b1287-105">Contains the Rich Text Format (RTF) version of the message text, usually in compressed form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b1287-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b1287-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b1287-107">PR_RTF_COMPRESSED</span><span class="sxs-lookup"><span data-stu-id="b1287-107">PR_RTF_COMPRESSED</span></span>  <br/> |
|<span data-ttu-id="b1287-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b1287-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b1287-109">0x1009</span><span class="sxs-lookup"><span data-stu-id="b1287-109">0x1009</span></span>  <br/> |
|<span data-ttu-id="b1287-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b1287-110">Data type:</span></span>  <br/> |<span data-ttu-id="b1287-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="b1287-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="b1287-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b1287-112">Area:</span></span>  <br/> |<span data-ttu-id="b1287-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="b1287-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b1287-114">说明</span><span class="sxs-lookup"><span data-stu-id="b1287-114">Remarks</span></span>

<span data-ttu-id="b1287-115">此属性包含相同的消息文本作为**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，但以 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="b1287-115">This property contains the same message text as the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property but in RTF.</span></span> 
  
<span data-ttu-id="b1287-116">压缩的窗体中通常存储以 rtf 格式的消息文本。</span><span class="sxs-lookup"><span data-stu-id="b1287-116">Message text in RTF is normally stored in compressed form.</span></span> <span data-ttu-id="b1287-117">但是，某些系统不压缩格式的文本。</span><span class="sxs-lookup"><span data-stu-id="b1287-117">However, some systems do not compress formatted text.</span></span> <span data-ttu-id="b1287-118">若要容纳它们，MAPI，提供了标识未压缩的 RTF 和**STORE_UNCOMPRESSED_RTF**标志**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的邮件流标头的 dwMagicUncompressedRTF 值存储以指示它可以存储未压缩的 RTF。</span><span class="sxs-lookup"><span data-stu-id="b1287-118">To accommodate them, MAPI provides the dwMagicUncompressedRTF value for a stream header to identify uncompressed RTF, and the **STORE_UNCOMPRESSED_RTF** flag in **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) for the message store to indicate it can store uncompressed RTF.</span></span> 
  
<span data-ttu-id="b1287-119">若要获得此属性的内容，呼叫**OpenProperty**，然后呼叫[WrapCompressedRTFStream](wrapcompressedrtfstream.md) **MAPI_READ**标志。</span><span class="sxs-lookup"><span data-stu-id="b1287-119">To obtain the contents of this property, call **OpenProperty**, then call [WrapCompressedRTFStream](wrapcompressedrtfstream.md) with the **MAPI_READ** flag.</span></span> <span data-ttu-id="b1287-120">要写入此属性，请使用**MAPI_MODIFY**和**MAPI_CREATE**标志打开它。</span><span class="sxs-lookup"><span data-stu-id="b1287-120">To write into this property, open it with the **MAPI_MODIFY** and **MAPI_CREATE** flags.</span></span> <span data-ttu-id="b1287-121">这样可确保新数据完全替换任何旧数据和使用存储更新的最小数目执行写入操作。</span><span class="sxs-lookup"><span data-stu-id="b1287-121">This ensures that the new data completely replace any old data and that the writes are performed using the minimum number of store updates.</span></span> 
  
<span data-ttu-id="b1287-122">支持 RTF 的消息存储忽略空格消息文本中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="b1287-122">Message stores that support RTF ignore any changes to white space in the message text.</span></span> <span data-ttu-id="b1287-123">当**PR_BODY**存储首次时，消息存储还生成该文件，并将此属性存储。</span><span class="sxs-lookup"><span data-stu-id="b1287-123">When **PR_BODY** is stored for the first time, the message store also generates and stores this property.</span></span> <span data-ttu-id="b1287-124">如果[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法之后调用和已修改**PR_BODY** ，消息存储调用[RTFSync](rtfsync.md)函数，以确保与 RTF 版本同步。</span><span class="sxs-lookup"><span data-stu-id="b1287-124">If the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is subsequently called and **PR_BODY** has been modified, the message store calls the [RTFSync](rtfsync.md) function to ensure synchronization with the RTF version.</span></span> <span data-ttu-id="b1287-125">属性如果只已更改的空白区域，将保留不变。</span><span class="sxs-lookup"><span data-stu-id="b1287-125">If only white space has been changed, the properties are left unchanged.</span></span> <span data-ttu-id="b1287-126">这会保留任何不常用 RTF 格式时通过非 RTF 感知客户端的消息传输和邮件系统。</span><span class="sxs-lookup"><span data-stu-id="b1287-126">This preserves any nontrivial RTF formatting when the message travels through non-RTF-aware clients and messaging systems.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b1287-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="b1287-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b1287-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="b1287-128">Protocol specifications</span></span>

<span data-ttu-id="b1287-129">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1287-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1287-130">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b1287-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b1287-131">[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1287-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1287-132">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="b1287-132">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="b1287-133">[[MS OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1287-133">[[MS-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1287-134">进行编码和解码 RTF 邮件正文中的压缩文件的流。</span><span class="sxs-lookup"><span data-stu-id="b1287-134">Encodes and decodes a compressed stream in RTF message bodies.</span></span>
    
<span data-ttu-id="b1287-135">[[MS OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b1287-135">[[MS-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b1287-136">邮件和附件的 RTF body 属性中封装 （如 HTML) 的其他内容的格式。</span><span class="sxs-lookup"><span data-stu-id="b1287-136">Encapsulates additional content formats (such as HTML) within the RTF body property of messages and attachments.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b1287-137">头文件</span><span class="sxs-lookup"><span data-stu-id="b1287-137">Header files</span></span>

<span data-ttu-id="b1287-138">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b1287-138">Mapidefs.h</span></span>
  
> <span data-ttu-id="b1287-139">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b1287-139">Provides data type definitions.</span></span>
    
<span data-ttu-id="b1287-140">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b1287-140">Mapitags.h</span></span>
  
> <span data-ttu-id="b1287-141">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b1287-141">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b1287-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1287-142">See also</span></span>



[<span data-ttu-id="b1287-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b1287-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b1287-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b1287-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b1287-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b1287-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b1287-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b1287-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

