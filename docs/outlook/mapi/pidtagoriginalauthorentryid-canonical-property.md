---
title: PidTagOriginalAuthorEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalAuthorEntryId
api_type:
- COM
ms.assetid: 34654660-b003-42f5-9fcd-24ebaccd735d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 03244fb240231a105b0a25a0797c13b9bf7f7a80
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777912"
---
# <a name="pidtagoriginalauthorentryid-canonical-property"></a><span data-ttu-id="88c93-103">PidTagOriginalAuthorEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="88c93-103">PidTagOriginalAuthorEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="88c93-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="88c93-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="88c93-105">包含一条消息，即之前正在转发或答复邮件的第一个版本的作者的项标识符。</span><span class="sxs-lookup"><span data-stu-id="88c93-105">Contains the entry identifier of the author of the first version of a message, that is, the message before being forwarded or replied to.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="88c93-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="88c93-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="88c93-107">PR_ORIGINAL_AUTHOR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="88c93-107">PR_ORIGINAL_AUTHOR_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="88c93-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="88c93-108">Identifier:</span></span>  <br/> |<span data-ttu-id="88c93-109">0x004C</span><span class="sxs-lookup"><span data-stu-id="88c93-109">0x004C</span></span>  <br/> |
|<span data-ttu-id="88c93-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="88c93-110">Data type:</span></span>  <br/> |<span data-ttu-id="88c93-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="88c93-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="88c93-112">区域：</span><span class="sxs-lookup"><span data-stu-id="88c93-112">Area:</span></span>  <br/> |<span data-ttu-id="88c93-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="88c93-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="88c93-114">说明</span><span class="sxs-lookup"><span data-stu-id="88c93-114">Remarks</span></span>

<span data-ttu-id="88c93-115">此属性是一个邮件的作者的地址属性。</span><span class="sxs-lookup"><span data-stu-id="88c93-115">This property is one of the address properties for the author of a message.</span></span> <span data-ttu-id="88c93-116">在首次提交邮件，客户端应用程序应将此属性设置为**PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)) 的值。</span><span class="sxs-lookup"><span data-stu-id="88c93-116">At first submission of the message, the client application should set this property to the value of **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)).</span></span> <span data-ttu-id="88c93-117">当转发或答复邮件永远不会更改它。</span><span class="sxs-lookup"><span data-stu-id="88c93-117">It is never changed when the message is forwarded or replied to.</span></span> 
  
<span data-ttu-id="88c93-118">原始作者属性允许保留来自域外部的本地消息的信息。</span><span class="sxs-lookup"><span data-stu-id="88c93-118">The original author property allows for preservation of information from outside the local messaging domain.</span></span> <span data-ttu-id="88c93-119">邮件到达后从其他邮件的域，如从 Internet，此属性提供了一种方法，以确保该原始信息不会丢失。</span><span class="sxs-lookup"><span data-stu-id="88c93-119">When a message arrives from another messaging domain, such as from the Internet, this property provides a way to ensure that original information is not lost.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="88c93-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="88c93-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="88c93-121">头文件</span><span class="sxs-lookup"><span data-stu-id="88c93-121">Header files</span></span>

<span data-ttu-id="88c93-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="88c93-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="88c93-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="88c93-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="88c93-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="88c93-124">Mapitags.h</span></span>
  
> <span data-ttu-id="88c93-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="88c93-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="88c93-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88c93-126">See also</span></span>



[<span data-ttu-id="88c93-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="88c93-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="88c93-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="88c93-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="88c93-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="88c93-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="88c93-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="88c93-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

