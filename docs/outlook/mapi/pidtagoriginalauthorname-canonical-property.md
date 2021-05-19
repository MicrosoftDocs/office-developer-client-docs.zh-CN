---
title: PidTagOriginalAuthorName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorNam
api_type:
- COM
ms.assetid: beb23742-d844-4d90-9b13-1ad376d4206c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bb62f3a44c9f17070db969683891fb2e2d62eb5e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355774"
---
# <a name="pidtagoriginalauthorname-canonical-property"></a><span data-ttu-id="86f39-103">PidTagOriginalAuthorName 规范属性</span><span class="sxs-lookup"><span data-stu-id="86f39-103">PidTagOriginalAuthorName Canonical Property</span></span>

  
  
<span data-ttu-id="86f39-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86f39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86f39-105">包含显示名称第一个版本的邮件，即转发或答复之前的邮件的作者的附件。</span><span class="sxs-lookup"><span data-stu-id="86f39-105">Contains the display name of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86f39-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="86f39-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="86f39-107">PR_ORIGINAL_AUTHOR_NAME、PR_ORIGINAL_AUTHOR_NAME_A、PR_ORIGINAL_AUTHOR_NAME_W</span><span class="sxs-lookup"><span data-stu-id="86f39-107">PR_ORIGINAL_AUTHOR_NAME, PR_ORIGINAL_AUTHOR_NAME_A, PR_ORIGINAL_AUTHOR_NAME_W</span></span>  <br/> |
|<span data-ttu-id="86f39-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="86f39-108">Identifier:</span></span>  <br/> |<span data-ttu-id="86f39-109">0x004D</span><span class="sxs-lookup"><span data-stu-id="86f39-109">0x004D</span></span>  <br/> |
|<span data-ttu-id="86f39-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="86f39-110">Data type:</span></span>  <br/> |<span data-ttu-id="86f39-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="86f39-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="86f39-112">区域：</span><span class="sxs-lookup"><span data-stu-id="86f39-112">Area:</span></span>  <br/> |<span data-ttu-id="86f39-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="86f39-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="86f39-114">备注</span><span class="sxs-lookup"><span data-stu-id="86f39-114">Remarks</span></span>

<span data-ttu-id="86f39-115">这些属性是邮件作者的地址属性示例。</span><span class="sxs-lookup"><span data-stu-id="86f39-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="86f39-116">首次提交邮件时，客户端应用程序应该将这些属性设置为 PR_SENDER_NAME ([PidTagSenderName](pidtagsendername-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="86f39-116">At first submission of the message, the client application should set these properties to the value of **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)).</span></span> <span data-ttu-id="86f39-117">转发或答复邮件时从不更改。</span><span class="sxs-lookup"><span data-stu-id="86f39-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="86f39-118">原始作者属性允许保留来自本地邮件域外部的信息。</span><span class="sxs-lookup"><span data-stu-id="86f39-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="86f39-119">当邮件从另一个邮件域（如 Internet）到达时，这些属性提供了一种确保原始信息不会丢失的方法。</span><span class="sxs-lookup"><span data-stu-id="86f39-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="86f39-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="86f39-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="86f39-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="86f39-121">Protocol specifications</span></span>

<span data-ttu-id="86f39-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="86f39-122">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="86f39-123">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="86f39-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="86f39-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="86f39-124">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="86f39-125">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="86f39-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="86f39-126">头文件</span><span class="sxs-lookup"><span data-stu-id="86f39-126">Header files</span></span>

<span data-ttu-id="86f39-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="86f39-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="86f39-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="86f39-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="86f39-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="86f39-129">Mapitags.h</span></span>
  
> <span data-ttu-id="86f39-130">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="86f39-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="86f39-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86f39-131">See also</span></span>



[<span data-ttu-id="86f39-132">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="86f39-132">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="86f39-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="86f39-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="86f39-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="86f39-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="86f39-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="86f39-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="86f39-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="86f39-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

