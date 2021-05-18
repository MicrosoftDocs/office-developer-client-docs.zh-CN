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
ms.openlocfilehash: 243a59798980d8c0cfaf1a726d6408dbd66ebba8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326633"
---
# <a name="pidtagbody-canonical-property"></a><span data-ttu-id="e590b-103">PidTagBody 规范属性</span><span class="sxs-lookup"><span data-stu-id="e590b-103">PidTagBody Canonical Property</span></span>

  
  
<span data-ttu-id="e590b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e590b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e590b-105">包含消息文本。</span><span class="sxs-lookup"><span data-stu-id="e590b-105">Contains the message text.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e590b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e590b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e590b-107">PR_BODY、PR_BODY_A、PR_BODY_W</span><span class="sxs-lookup"><span data-stu-id="e590b-107">PR_BODY, PR_BODY_A, PR_BODY_W</span></span>  <br/> |
|<span data-ttu-id="e590b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e590b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e590b-109">0x1000</span><span class="sxs-lookup"><span data-stu-id="e590b-109">0x1000</span></span>  <br/> |
|<span data-ttu-id="e590b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e590b-110">Data type:</span></span>  <br/> |<span data-ttu-id="e590b-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="e590b-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="e590b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e590b-112">Area:</span></span>  <br/> |<span data-ttu-id="e590b-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="e590b-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e590b-114">备注</span><span class="sxs-lookup"><span data-stu-id="e590b-114">Remarks</span></span>

<span data-ttu-id="e590b-115">这些属性通常仅用于 IPM (的) 。</span><span class="sxs-lookup"><span data-stu-id="e590b-115">These properties are typically used only in an interpersonal message (IPM).</span></span> 
  
<span data-ttu-id="e590b-116">支持 RTF 格式的邮件存储 (RTF) 忽略对邮件文本中的空格的任何更改。</span><span class="sxs-lookup"><span data-stu-id="e590b-116">Message stores that support Rich Text Format (RTF) ignore any changes to white space in the message text.</span></span> <span data-ttu-id="e590b-117">首次 **PR_BODY** 时，邮件存储还会生成并存储 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性，即消息文本的 RTF 版本。</span><span class="sxs-lookup"><span data-stu-id="e590b-117">When **PR_BODY** is stored for the first time, the message store also generates and stores the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property, the RTF version of the message text.</span></span> <span data-ttu-id="e590b-118">如果[随后调用 IMAPIProp：：SaveChanges](imapiprop-savechanges.md)方法，PR_BODY修改了该函数，则消息存储将调用[RTFSync](rtfsync.md)函数以确保与 RTF 版本同步。</span><span class="sxs-lookup"><span data-stu-id="e590b-118">If the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method is subsequently called and **PR_BODY** has been modified, the message store calls the [RTFSync](rtfsync.md) function to ensure synchronization with the RTF version.</span></span> <span data-ttu-id="e590b-119">如果仅更改了空格，则属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="e590b-119">If only white space has been changed, the properties are left unchanged.</span></span> <span data-ttu-id="e590b-120">这将在邮件通过非 RTF 感知客户端和邮件系统时保留任何非实时 RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="e590b-120">This preserves any nontrivial RTF formatting when the message travels through non-RTF-aware clients and messaging systems.</span></span> 
  
<span data-ttu-id="e590b-121">此属性的值必须用运行 MAPI 的操作系统的代码页表示。</span><span class="sxs-lookup"><span data-stu-id="e590b-121">The value for this property must be expressed in the code page of the operating system that MAPI is running on.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e590b-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="e590b-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e590b-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="e590b-123">Protocol specifications</span></span>

<span data-ttu-id="e590b-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e590b-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e590b-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e590b-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e590b-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e590b-126">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e590b-127">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="e590b-127">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e590b-128">头文件</span><span class="sxs-lookup"><span data-stu-id="e590b-128">Header files</span></span>

<span data-ttu-id="e590b-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e590b-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="e590b-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e590b-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="e590b-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e590b-131">Mapitags.h</span></span>
  
> <span data-ttu-id="e590b-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e590b-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e590b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e590b-133">See also</span></span>



[<span data-ttu-id="e590b-134">PidTagRtfInSync 规范属性</span><span class="sxs-lookup"><span data-stu-id="e590b-134">PidTagRtfInSync Canonical Property</span></span>](pidtagrtfinsync-canonical-property.md)


[<span data-ttu-id="e590b-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e590b-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e590b-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e590b-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e590b-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e590b-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e590b-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e590b-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

