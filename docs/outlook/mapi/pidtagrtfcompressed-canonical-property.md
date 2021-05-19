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
# <a name="pidtagrtfcompressed-canonical-property"></a><span data-ttu-id="0ae40-103">PidTagRtfCompressed 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ae40-103">PidTagRtfCompressed Canonical Property</span></span>

  
  
<span data-ttu-id="0ae40-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ae40-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ae40-105">包含 RTF 格式 (RTF) 格式的邮件文本版本，通常采用压缩形式。</span><span class="sxs-lookup"><span data-stu-id="0ae40-105">Contains the Rich Text Format (RTF) version of the message text, usually in compressed form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0ae40-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0ae40-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0ae40-107">PR_RTF_COMPRESSED</span><span class="sxs-lookup"><span data-stu-id="0ae40-107">PR_RTF_COMPRESSED</span></span>  <br/> |
|<span data-ttu-id="0ae40-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0ae40-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0ae40-109">0x1009</span><span class="sxs-lookup"><span data-stu-id="0ae40-109">0x1009</span></span>  <br/> |
|<span data-ttu-id="0ae40-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0ae40-110">Data type:</span></span>  <br/> |<span data-ttu-id="0ae40-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="0ae40-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="0ae40-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0ae40-112">Area:</span></span>  <br/> |<span data-ttu-id="0ae40-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="0ae40-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0ae40-114">备注</span><span class="sxs-lookup"><span data-stu-id="0ae40-114">Remarks</span></span>

<span data-ttu-id="0ae40-115">此属性包含与[PidTagBody](pidtagbody-canonical-property.md) 属性中的 PR_BODY (文本) RTF 中相同的消息文本。</span><span class="sxs-lookup"><span data-stu-id="0ae40-115">This property contains the same message text as the **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) property but in RTF.</span></span> 
  
<span data-ttu-id="0ae40-116">RTF 中的邮件文本通常以压缩形式存储。</span><span class="sxs-lookup"><span data-stu-id="0ae40-116">Message text in RTF is normally stored in compressed form.</span></span> <span data-ttu-id="0ae40-117">但是，某些系统不压缩格式化文本。</span><span class="sxs-lookup"><span data-stu-id="0ae40-117">However, some systems do not compress formatted text.</span></span> <span data-ttu-id="0ae40-118">为了容纳它们，MAPI 为流标头提供 dwMagicUncompressedRTF 值以标识未压缩的 RTF，为 **邮件** 存储提供 PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 中的 **STORE_UNCOMPRESSED_RTF** 标志，以指示它可以存储未压缩的 RTF。</span><span class="sxs-lookup"><span data-stu-id="0ae40-118">To accommodate them, MAPI provides the dwMagicUncompressedRTF value for a stream header to identify uncompressed RTF, and the **STORE_UNCOMPRESSED_RTF** flag in **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) for the message store to indicate it can store uncompressed RTF.</span></span> 
  
<span data-ttu-id="0ae40-119">若要获取此属性的内容，请调用 **OpenProperty**，然后调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md) 和 **MAPI_READ** 标志。</span><span class="sxs-lookup"><span data-stu-id="0ae40-119">To obtain the contents of this property, call **OpenProperty**, then call [WrapCompressedRTFStream](wrapcompressedrtfstream.md) with the **MAPI_READ** flag.</span></span> <span data-ttu-id="0ae40-120">若要写入此属性，请用 MAPI_MODIFY **和** MAPI_CREATE **打开它** 。</span><span class="sxs-lookup"><span data-stu-id="0ae40-120">To write into this property, open it with the **MAPI_MODIFY** and **MAPI_CREATE** flags.</span></span> <span data-ttu-id="0ae40-121">这可确保新数据完全替换任何旧数据，并确保使用最少数量的存储更新执行写入。</span><span class="sxs-lookup"><span data-stu-id="0ae40-121">This ensures that the new data completely replace any old data and that the writes are performed using the minimum number of store updates.</span></span> 
  
<span data-ttu-id="0ae40-122">支持 RTF 的邮件存储将忽略对邮件文本中的空格的任何更改。</span><span class="sxs-lookup"><span data-stu-id="0ae40-122">Message stores that support RTF ignore any changes to white space in the message text.</span></span> <span data-ttu-id="0ae40-123">首次 **PR_BODY** 时，邮件存储还会生成并存储此属性。</span><span class="sxs-lookup"><span data-stu-id="0ae40-123">When **PR_BODY** is stored for the first time, the message store also generates and stores this property.</span></span> <span data-ttu-id="0ae40-124">如果[随后调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，PR_BODY修改了该函数，则消息存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。</span><span class="sxs-lookup"><span data-stu-id="0ae40-124">If the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is subsequently called and **PR_BODY** has been modified, the message store calls the [RTFSync](rtfsync.md) function to ensure synchronization with the RTF version.</span></span> <span data-ttu-id="0ae40-125">如果仅更改了空格，则属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="0ae40-125">If only white space has been changed, the properties are left unchanged.</span></span> <span data-ttu-id="0ae40-126">这将在邮件通过非 RTF 感知客户端和邮件系统时保留任何非实时 RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="0ae40-126">This preserves any nontrivial RTF formatting when the message travels through non-RTF-aware clients and messaging systems.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0ae40-127">相关资源</span><span class="sxs-lookup"><span data-stu-id="0ae40-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0ae40-128">协议规范</span><span class="sxs-lookup"><span data-stu-id="0ae40-128">Protocol specifications</span></span>

<span data-ttu-id="0ae40-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ae40-129">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ae40-130">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="0ae40-130">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0ae40-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ae40-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ae40-132">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="0ae40-132">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="0ae40-133">[[MS-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ae40-133">[[MS-OXRTFCP]](https://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ae40-134">对 RTF 邮件正文中的压缩流进行编码和解码。</span><span class="sxs-lookup"><span data-stu-id="0ae40-134">Encodes and decodes a compressed stream in RTF message bodies.</span></span>
    
<span data-ttu-id="0ae40-135">[[MS-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ae40-135">[[MS-OXRTFEX]](https://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0ae40-136">封装邮件和附件 (RTF 正文) HTML 格式等附加内容格式。</span><span class="sxs-lookup"><span data-stu-id="0ae40-136">Encapsulates additional content formats (such as HTML) within the RTF body property of messages and attachments.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0ae40-137">头文件</span><span class="sxs-lookup"><span data-stu-id="0ae40-137">Header files</span></span>

<span data-ttu-id="0ae40-138">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0ae40-138">Mapidefs.h</span></span>
  
> <span data-ttu-id="0ae40-139">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0ae40-139">Provides data type definitions.</span></span>
    
<span data-ttu-id="0ae40-140">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0ae40-140">Mapitags.h</span></span>
  
> <span data-ttu-id="0ae40-141">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0ae40-141">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0ae40-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ae40-142">See also</span></span>



[<span data-ttu-id="0ae40-143">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0ae40-143">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0ae40-144">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0ae40-144">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0ae40-145">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0ae40-145">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0ae40-146">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0ae40-146">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

