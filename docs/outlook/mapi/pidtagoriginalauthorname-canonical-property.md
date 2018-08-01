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
ms.openlocfilehash: 4b2f47f503caa32a1bdcd287e2fa5e894d667573
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777918"
---
# <a name="pidtagoriginalauthorname-canonical-property"></a><span data-ttu-id="ef670-103">PidTagOriginalAuthorName 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef670-103">PidTagOriginalAuthorName Canonical Property</span></span>

  
  
<span data-ttu-id="ef670-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ef670-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ef670-105">包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ef670-105">Contains the display name of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ef670-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ef670-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ef670-107">PR_ORIGINAL_AUTHOR_NAME，PR_ORIGINAL_AUTHOR_NAME_A，PR_ORIGINAL_AUTHOR_NAME_W</span><span class="sxs-lookup"><span data-stu-id="ef670-107">PR_ORIGINAL_AUTHOR_NAME, PR_ORIGINAL_AUTHOR_NAME_A, PR_ORIGINAL_AUTHOR_NAME_W</span></span>  <br/> |
|<span data-ttu-id="ef670-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ef670-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ef670-109">0x004D</span><span class="sxs-lookup"><span data-stu-id="ef670-109">0x004D</span></span>  <br/> |
|<span data-ttu-id="ef670-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ef670-110">Data type:</span></span>  <br/> |<span data-ttu-id="ef670-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="ef670-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="ef670-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ef670-112">Area:</span></span>  <br/> |<span data-ttu-id="ef670-113">电子邮件</span><span class="sxs-lookup"><span data-stu-id="ef670-113">Email</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ef670-114">说明</span><span class="sxs-lookup"><span data-stu-id="ef670-114">Remarks</span></span>

<span data-ttu-id="ef670-115">这些属性是邮件的作者的地址属性的示例。</span><span class="sxs-lookup"><span data-stu-id="ef670-115">These properties are examples of the address properties for the author of a message.</span></span> <span data-ttu-id="ef670-116">在首次提交邮件，客户端应用程序应为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 的值来设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="ef670-116">At first submission of the message, the client application should set these properties to the value of **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)).</span></span> <span data-ttu-id="ef670-117">当转发或答复邮件永远不会更改它。</span><span class="sxs-lookup"><span data-stu-id="ef670-117">It is never changed when the message is forwarded or replied to.</span></span>
  
<span data-ttu-id="ef670-118">原始作者属性允许保留来自域外部的本地消息的信息。</span><span class="sxs-lookup"><span data-stu-id="ef670-118">The original author properties allow for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="ef670-119">当邮件到达从其他邮件的域时，如从 Internet，这些属性提供一种方法，以确保原始信息不会丢失。</span><span class="sxs-lookup"><span data-stu-id="ef670-119">When a message arrives from another messaging domain, such as from the Internet, these properties provide a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ef670-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="ef670-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ef670-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="ef670-121">Protocol specifications</span></span>

<span data-ttu-id="ef670-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef670-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef670-123">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ef670-123">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ef670-124">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ef670-124">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ef670-125">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="ef670-125">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ef670-126">头文件</span><span class="sxs-lookup"><span data-stu-id="ef670-126">Header files</span></span>

<span data-ttu-id="ef670-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ef670-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="ef670-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ef670-128">Provides data type definitions.</span></span>
    
<span data-ttu-id="ef670-129">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ef670-129">Mapitags.h</span></span>
  
> <span data-ttu-id="ef670-130">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ef670-130">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ef670-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef670-131">See also</span></span>



[<span data-ttu-id="ef670-132">PidTagDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef670-132">PidTagDisplayName Canonical Property</span></span>](pidtagdisplayname-canonical-property.md)


[<span data-ttu-id="ef670-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ef670-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ef670-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ef670-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ef670-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ef670-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ef670-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ef670-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

