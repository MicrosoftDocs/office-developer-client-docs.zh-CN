---
title: PidTagBody 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBody
api_type:
- HeaderDef
ms.assetid: 47c0d0fe-4d57-4b81-bdb5-336de85c194c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbcfdf44044e3cf9e42b0f0503928c9f8720ec1f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574417"
---
# <a name="pidtagbody-canonical-property"></a><span data-ttu-id="888cc-103">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="888cc-103">PidTagBody Canonical Property</span></span>

  
  
<span data-ttu-id="888cc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="888cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="888cc-105">包含消息文本。</span><span class="sxs-lookup"><span data-stu-id="888cc-105">Contains the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="888cc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="888cc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="888cc-107">PR_BODY，PR_BODY_A，PR_BODY_W</span><span class="sxs-lookup"><span data-stu-id="888cc-107">PR_BODY, PR_BODY_A, PR_BODY_W</span></span>  <br/> |
|<span data-ttu-id="888cc-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="888cc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="888cc-109">0x1000</span><span class="sxs-lookup"><span data-stu-id="888cc-109">0x1000</span></span>  <br/> |
|<span data-ttu-id="888cc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="888cc-110">Data type:</span></span>  <br/> |<span data-ttu-id="888cc-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="888cc-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="888cc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="888cc-112">Area:</span></span>  <br/> |<span data-ttu-id="888cc-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="888cc-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="888cc-114">注解</span><span class="sxs-lookup"><span data-stu-id="888cc-114">Remarks</span></span>

<span data-ttu-id="888cc-115">通常只能在人际邮件 (IPM) 中使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="888cc-115">These properties are typically used only in an interpersonal message (IPM).</span></span> 
  
<span data-ttu-id="888cc-116">支持富文本格式 (RTF) 的消息存储忽略空格消息文本中的任何更改。</span><span class="sxs-lookup"><span data-stu-id="888cc-116">Message stores that support Rich Text Format (RTF) ignore any changes to white space in the message text.</span></span> <span data-ttu-id="888cc-117">当**PR_BODY**存储首次时，消息存储还将生成该文件，并将存储**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，消息文本的 RTF 版本。</span><span class="sxs-lookup"><span data-stu-id="888cc-117">When **PR_BODY** is stored for the first time, the message store also generates and stores the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, the RTF version of the message text.</span></span> <span data-ttu-id="888cc-118">如果[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法之后调用和已修改**PR_BODY** ，消息存储调用[RTFSync](rtfsync.md)函数，以确保与 RTF 版本同步。</span><span class="sxs-lookup"><span data-stu-id="888cc-118">If the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is subsequently called and **PR_BODY** has been modified, the message store calls the [RTFSync](rtfsync.md) function to ensure synchronization with the RTF version.</span></span> <span data-ttu-id="888cc-119">属性如果只已更改的空白区域，将保留不变。</span><span class="sxs-lookup"><span data-stu-id="888cc-119">If only white space has been changed, the properties are left unchanged.</span></span> <span data-ttu-id="888cc-120">这会保留任何不常用 RTF 格式时通过非 RTF 感知客户端的消息传输和邮件系统。</span><span class="sxs-lookup"><span data-stu-id="888cc-120">This preserves any nontrivial RTF formatting when the message travels through non-RTF-aware clients and messaging systems.</span></span> 
  
<span data-ttu-id="888cc-121">此属性的值必须用表示操作系统 MAPI 正在运行的代码页。</span><span class="sxs-lookup"><span data-stu-id="888cc-121">The value for this property must be expressed in the code page of the operating system that MAPI is running on.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="888cc-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="888cc-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="888cc-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="888cc-123">Protocol specifications</span></span>

<span data-ttu-id="888cc-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="888cc-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="888cc-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="888cc-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="888cc-126">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="888cc-126">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="888cc-127">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="888cc-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="888cc-128">头文件</span><span class="sxs-lookup"><span data-stu-id="888cc-128">Header files</span></span>

<span data-ttu-id="888cc-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="888cc-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="888cc-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="888cc-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="888cc-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="888cc-131">Mapitags.h</span></span>
  
> <span data-ttu-id="888cc-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="888cc-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="888cc-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="888cc-133">See also</span></span>



[<span data-ttu-id="888cc-134">PidTagRtfInSync 规范属性</span><span class="sxs-lookup"><span data-stu-id="888cc-134">PidTagRtfInSync Canonical Property</span></span>](pidtagrtfinsync-canonical-property.md)


[<span data-ttu-id="888cc-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="888cc-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="888cc-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="888cc-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="888cc-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="888cc-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="888cc-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="888cc-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

